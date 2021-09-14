<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  data(){
    return{
      apiKey: '65b48d566cec14fc37b043bd2741cf71',
      city: 'Cebu'
    }
  },
  getWeather(){
    axios.get(`api.openweathermap.org/data/2.5/weather?q=${this.city},{state code}&appid=${this.apiKey}`)
  },
  created(){
    this.getWeather();
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
