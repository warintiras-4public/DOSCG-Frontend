<template>
  <header>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/xyz">A B C</router-link> |
      <router-link to="/abc">X Y Z</router-link> |
      <router-link to="/direction">Direction</router-link> |
      <router-link to="/resume">Resume</router-link>
    </div>
    <router-view/>
  </header>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
