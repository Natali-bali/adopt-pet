<template>
  <div id="app">
    <app-header></app-header>
    <b-container>
      <router-view/>
    </b-container>
  </div>
</template>
<script>
import header from './views/Header.vue'
export default {
  components: {
    'app-header': header
  }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
