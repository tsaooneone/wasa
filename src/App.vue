<template>
  <div id="app">
    <AppHeader />
    <div class="container">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss">
body{
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  nav {
    padding: 30px;

    a {
      font-weight: bold;
      color: #2c3e50;

      &.router-link-exact-active {
        color: rgb(107, 171, 245);
      }
    }
  }
  .container{
    width: 80vw;
    margin: 0 auto;
  }
}
</style>

<script>
import '@/index.scss'
import AppHeader from '@/components/layouts/AppHeader.vue'

export default {
  name: 'App',
  components: {
    AppHeader
  }
}
</script>
