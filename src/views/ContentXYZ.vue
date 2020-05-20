<template>
  <div id="app">
      <b-container>
        <b-row>
            <b-col>Given X, Y, 5, 9, 15, 23, Z, find the values of X, Y, Z</b-col>
        </b-row>
        <b-row>
            <b-col>x is {{XYZ.x}}</b-col>
        </b-row>
        <b-row>
            <b-col>y is {{XYZ.y}}</b-col>
        </b-row>
        <b-row>
            <b-col>z is {{XYZ.z}}</b-col>
        </b-row>
    </b-container>
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
      XYZ: {}
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/xyz')
    
    .then((res) => {
      console.log(res.data);
      this.XYZ = res.data;
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
