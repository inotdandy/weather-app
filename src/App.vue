<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data(){
    return{
      apiKey: process.env.VUE_APP_WEATHER_API,
      city: 'Ormoc'
    }
  },
  methods: {
      getCurrentWeather(){
        axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.apiKey}`)
        .then(res => console.log(res.data))
        .catch(err => console.log(err))
      }
  },
  created(){
    this.getCurrentWeather();
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Quicksand', sans-serif;
}

</style>
