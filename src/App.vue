<template>
  <div id="app">
    
    <router-view/>
  </div>
</template>

<script>
import axios from "../node_modules/axios"
export default {
  name: "App",
  data(){
    return{
      APIKey: "eae090fd99ea56751ecd5654a1e9034a",
      city: "Detroit",
      BaseUrl: "api.openweathermap.org/data/2.5/"
    }
  },
  created(){
    this.getCurrentWeather()
  },
  methods: {
    getCurrentWeather(){
      axios
      .get(`${this.BaseUrl}weather?q=${this.city}&units=imperial&appid=${this.APIKey}`)
      .then(res => {
          console.log(res.data)
        });
    },
  },

};
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;  
}
</style>
