<template>
  <div id="app">
    <b-card bg-variant="light" header="How to travel from SCG to Central World?" class="text-left">
      <b-card-text>{{Content}}</b-card-text>
    </b-card>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      Content: {}
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/direction')
    
    .then((res) => {
      console.log(res.data);
      this.Content = res.data;
    })
    .catch(err=> console.log(err));
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
