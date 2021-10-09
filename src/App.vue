<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
body {
  background: url(https://n.sinaimg.cn/default/transform/350/w2840h710/20210930/60f4-5fc0114941cff22a67ebcdb5c5460c3e.png) no-repeat 50% 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
