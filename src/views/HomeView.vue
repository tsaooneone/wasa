<template>
    <div :class='theme === "light" ? "light" : theme === "dark" ? "dark" : ""'>
        {{ this.$theme }}
        <button @click='theme = "dark"'>Dark</button>
        <button @click='theme = "light"'>Light</button>
    </div>
</template>

<style lang="scss">
    button {
        margin: 10px;
    }
</style>

<script>
export default {
  name: 'HomeView',
  data () {
    return {
      theme: this.$theme
    }
  },
  updated () {
    this.$theme = this.theme
  }
}
</script>
