<template>
  <div id="app">
    <nav>
      <button class="icon-bar" @click="openNav">&#9776;</button>
    </nav>

    <div id="mySidenav" class="sidenav-container">
      <br />
      <router-link class="r" to="/Details">
        <div class="Details" @click="closeNav"> Employee Details</div>
      </router-link>
      <br />
      <br />
      <router-link class="r" to="/Home">
        <div class="Home" @click="closeNav">Employee Login</div>
      </router-link>
      <br />
      <br />
      <router-link class="r" to="/">
        <div class="MainPage" @click="closeNav">Main</div>
      </router-link>
    </div>

    <div id="main">
      <router-view />
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  setup () {
    function openNav () {
      const styleWidth = document.getElementById('mySidenav').style.width

      if (styleWidth.includes('%')) {
        document.getElementById('mySidenav').style.width = '0'
      } else {
        document.getElementById('mySidenav').style.width = '15%'
      }
    }

    function closeNav () {
      document.getElementById('mySidenav').style.width = '0px'
    }

    return {
      openNav,
      closeNav
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif ;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}

nav {
  align-items: center;
  display: flex;
  position: relative;
  justify-content: space-between;
  align-items: center;
  padding: 10px 5%;
  background-color: #1a1a1a;
}

.sidenav-container {
  height: 100%;
  width: 0px;
  position: fixed;
  background-color: #646464;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.closebtn {
  font-size: 3rem;
  font-weight: 700;
  color: #1a1a1a;
  padding-right: 1rem;
}

.icon-bar {
  background-color: #ff0000 !important;
  align-items: left;
  display: flex;
}
.Home {
  color: #ffffff !important;
  font-size: 22px;
  text-decoration: none;
}
.Details {
  color: #fffefe !important;
  font-size: 22px;
  text-decoration: none;
}
.sidenav-container:hover {
  box-shadow: 0 8px 16px 0 rgb(29, 29, 29);
}
.r {
  color: #fffefe !important;
  font-size: 22px;
  text-decoration: none;
}
</style>
