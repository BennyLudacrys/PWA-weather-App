<template>
  <div class="card">
    <div class="card-body">
      <h2 class="card-title" v-if="dados">{{ dados[0] }}</h2>
      <div id="sun">
        <img
          v-if="dados[3] == 'clear sky'"
          src="../assets/1530392_weather_sun_sunny_temperature_icon.png"
        />
        <img
          v-if="dados[3] == 'scattered clouds'"
          src="../assets/1530369_weather_cloud_clouds_cloudy_icon.png"
        />
        <img
          v-if="dados[3] == 'broken clouds'"
          src="../assets/1530369_weather_cloud_clouds_cloudy_icon.png"
        />
        <img
          v-if="dados[3] == 'few clouds'"
          src="../assets/1530369_weather_cloud_clouds_cloudy_icon.png"
        />
        <img
          v-if="dados[3] == 'shower rain '"
          src="../assets/2682845_cloud_cloudy_forecast_rain_sun_icon.png"
        />
        <img
          v-if="dados[3] == 'rain'"
          src="../assets/2682845_cloud_cloudy_forecast_rain_sun_icon.png"
        />
      </div>
      <div id="graus">
        <h4><span>Min: </span>{{ dados[1] }}°C</h4>
        <h4><span>Max: </span> {{ dados[2] }}°C</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["dados"],
};
</script>

<style scoped>
#sun {
  display: flex;
  justify-content: center;
  height: 200px;
}

.card {
  width: 18rem;
  height: 350px;
  margin-top: 30px;
  background: #4e3863;
  color: white;
}

h2 {
  text-align: center;
}

h4 {
  font-size: 15px;
}

h4 span {
  font-size: 23px;
  color: rgb(8, 243, 243);
}

#graus {
  margin-top: 30px;
  font-style: italic;
  display: flex;
  width: 100%;
  justify-content: space-between;
}

</style>