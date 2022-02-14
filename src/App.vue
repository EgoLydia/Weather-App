<template>
  <div id="app"></div>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search...">
        <input type="text" class="search-bar" 
        placeholder="Search..." 
        v-model="query"
        @keypress="fetchWeather"
        ></div>
      <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
        <div class="location-box">
          <div class="location">{{weather.name}}, {{weather.sys.country}} </div>
          <div class="date">{{dateBuilder()}}</div>
        </div>

        <div class="weather-box">
          <div class="temp">{{Math.round(weather.main.temp)}}°c</div>
          <div class="weather">{{weather.weather[0].main}}</div>
        </div>
      </div>
    </main>
</template>

<script>
export default {
  name: 'app'
  data(){
    return{
      api_key: '582f58018e28370809832a36ffc87799'
  name: "App",
  data() {
    return {
      api_key: "582f58018e28370809832a36ffc87799",
      url_base: 'https://api.openweathermap.org/data/2.5/',
      query: '',
      weather: {}
    };
  },
  methods :{
    fetchWeather(e){
      if (e.key =='Enter'){
        fetch (`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
        .then(res => {
          return res.json();
        }).then(this.setResults);
      }
    },
    setResults(results){
      this.weather = results;
    },
    }
}
</script>

<style lang='scss' scoped>
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: Arial, Helvetica, sans-serif;
}
#app {
  background-image: url('./assets/cold-bg.jpg');
  background-size: contain;
  background-position: bottom;
  transition: 0.4s;
}

main{
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.75));
}

.search-box{
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar{
  display: flex;
  width: 100%;
  padding: 15px;
  color: #313131;
  font-size: 20px;

  appearance: none;
  border: none;
  outline: none;
  background: none;

  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}

.search-box .search-bar:focus{
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
    border-radius: 16px 0px 16px 0px;

}
</style>
