<template>
  <div id="app">
 
    <router-view/>
  </div>
</template>

<style lang="less">

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
   

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
