<template>
  <div>
    <section id="city-lists" class="section">
      <div class="container">
        <h1>{{item.name}}の天気情報</h1>
        <img :src="'https://openweathermap.org/img/w/'+item.weather[0].icon+'.png'" />
        <ul>
          <li>{{ weather }}</li>
          <li>温度：{{item.main.temp}}℃</li>
          <li>湿度：{{item.main.humidity}}％</li>
          <li>風速：{{item.wind.speed}}m</li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {
	async asyncData({route, app, error}) {
		try {
		  const item = await app.$axios.$get(`https://api.openweathermap.org/data/2.5/weather?q=${route.params.name},jp&units=metric&lang=ja&appid=${process.env.WEATHER_API_KEY}`)
		  let weather = "";
			switch (item.weather[0].main){
				case "Clear":
					weather = "晴れ";
					break;
				case "Rain":
					weather = "雨";
					break;
				case "Clouds":
					weather = "くもり";
					break;
				case "Snow":
					weather = "雪";
					break;
				default:
					weather = item.weather[0].main;
					break;
			}

		  return {
		    item,
		    weather
		  }
		} catch (err) {
			error({
				statusCode: err.response.status,
				message: err.response.data.message,
			});
		}
	}


}
</script>

<style scoped>
</style>
