<template>
  <div id="app" class="display-2">
    {{Content}}
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'XYZ',
  components: {
  },
  data() {
    return {
      Content: {}
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/xyz')
    
    .then((res) => {
      console.log(res.data);
      this.Content = res.data;
    })
    .catch(err=> console.log(err));
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
