<template>
  <div id="app">
    <b-container>
        <b-row>
            <b-col>When a = 21, ab = 23, and ac = -21, what are the values of b and c?</b-col>
        </b-row>
        <b-row>
            <b-col>b is {{Content.b}}</b-col>
        </b-row>
        <b-row>
            <b-col>c is {{Content.c}}</b-col>
        </b-row>
    </b-container>
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
    axios.get('http://localhost:3000/api/abc')
    
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
}
</style>
