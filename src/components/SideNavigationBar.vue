<template>
  <nav :class="{open: isOpened}">
  <div class="logo" @click="open">
    <i class="bx bx-menu menu-icon"></i>
    <span class="logo-name">Guest Book</span>
  </div>
  <div class="sidebar">
    <div class="logo">
      <i class="bx bx-menu menu-icon"></i>
      <span class="logo-name">Guest Book</span>
    </div>

    <div class="sidebar-content">
      <ul class="lists">
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-home-alt icon"></i>
            <span class="link">방명록</span>
          </a>
        </li>
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-bell icon"></i>
            <span class="link">재고 관리</span>
          </a>
        </li>
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-message-rounded icon"></i>
            <span class="link">Messages</span>
          </a>
        </li>
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-pie-chart-alt-2 icon"></i>
            <span class="link">Analytics</span>
          </a>
        </li>
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-heart icon"></i>
            <span class="link">Likes</span>
          </a>
        </li>
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-folder-open icon"></i>
            <span class="link">Files</span>
          </a>
        </li>
      </ul>

      <div class="bottom-cotent">
        <li class="list">
          <a href="#" class="nav-link">
            <i class="bx bx-cog icon"></i>
            <span class="link">Settings</span>
          </a>
        </li>
      </div>
    </div>
  </div>
</nav>
<section class="overlay" @click="close"></section>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      isOpened: false
    }
  },
  methods: {
    open(event) {
      console.log(event)
      this.isOpened = true;
    },
    close() {
      this.isOpened = false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  * {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: "Poppins", sans-serif;
}
body {
	min-height: 100%;
	background: #f4faff;
}
nav {
	position: fixed;
	top: 0;
	left: 0;
	height: 70px;
	width: 100%;
	display: flex;
	align-items: center;
	background: #fff;
	box-shadow: 0 0 1px rgba(0, 0, 0, 0.1);
	.logo {
		display: flex;
		align-items: center;
		margin: 0 24px;
	}
	.sidebar {
		position: fixed;
		top: 0;
		left: -100%;
		height: 100%;
		width: 260px;
		padding: 20px 0;
		background-color: #fff;
		box-shadow: 0 5px 1px rgba(0, 0, 0, 0.1);
		transition: all 0.4s ease;
	}
}
.logo {
	.menu-icon {
		color: #333;
		font-size: 24px;
		margin-right: 14px;
		cursor: pointer;
	}
	.logo-name {
		color: #333;
		font-size: 22px;
		font-weight: 500;
	}
}
nav.open {
	.sidebar {
		left: 0;
	}
	~ {
		.overlay {
			opacity: 1;
			left: 260px;
			pointer-events: auto;
		}
	}
}
.sidebar {
	.sidebar-content {
		display: flex;
		height: 100%;
		flex-direction: column;
		justify-content: space-between;
		padding: 30px 16px;
	}
}
.sidebar-content {
	.list {
		list-style: none;
	}
}
.list {
	.nav-link {
		display: flex;
		align-items: center;
		margin: 8px 0;
		padding: 14px 12px;
		border-radius: 8px;
		text-decoration: none;
	}
}
.lists {
	.nav-link {
    transition: background-color 0.25s ease;
		&:hover {
			background-color: #4070f4;
			.icon {
				color: #fff;
			}
			.link {
				color: #fff;
			}
		}
	}
}
.nav-link {
	.icon {
		margin-right: 14px;
		font-size: 20px;
		color: #707070;
	}
	.link {
		font-size: 16px;
		color: #707070;
		font-weight: 400;
	}
}
.overlay {
	position: fixed;
	top: 0;
	left: -100%;
	height: 1000vh;
	width: 200%;
	opacity: 0;
	pointer-events: none;
	transition: all 0.4s ease;
	background: rgba(0, 0, 0, 0.3);
}

</style>
