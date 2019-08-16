<template>
  <div id="app">
    <div class="container">
      <div class="navbar">
        <div id="nav">
          <div class="logo">Век живи, век учись!</div>
          <div>
            <router-link to="/">Home</router-link> |
            <router-link to="/courses">Courses</router-link> |
            <router-link to="/users">Users</router-link>
          </div>
        </div>
        <router-view />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
// COLORS
$lblack: #35495e;
$white: #ffffff;
$lgreen: #59b983;
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.navbar {
  width: 100%;
}

#nav {
  display: flex;
  justify-content: space-between;
  padding: 15px;
  background-color: $lblack;
  color: $white;
  a {
    // padding: auto 2% auto;
    font-weight: 400;
    color: $white;
    text-decoration: none;
    &.router-link-exact-active {
      color: $lgreen;
    }
  }
}
</style>
