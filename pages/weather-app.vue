<template>
  <v-container>
    <p class="text-xs-center">Weather App</p>

    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo">
        <v-text-field
          v-model="city"
          label="Enter City Name"
          solo
        ></v-text-field>
      </v-form>

      <v-layout>
        <v-flex xs12>
          <v-card color="blue-grey darken-2">
            <v-card-text>
              <v-layout>
                <v-flex class="t ext-xs-center">
                  <h4>Temperature</h4>
                  <span class="display-2">{{ weather.name }}</span>
                </v-flex>
                <p class="caption">{{ weather.weather[0].description }}</p>
                <p>Temperature : {{ temp() }} &deg;C</p>
                <p>Desc : {{ weather.weather[0].icon }}</p>
              </v-layout>
            </v-card-text>
          </v-card>
        </v-flex>
        <div class="font-weight-bold mr-8 mb-1 md3"></div>
      </v-layout>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const weather = await $axios.$get(
      `https://api.openweathermap.org/data/2.5/weather?q=Bekasi&appid=fe848d92ce456b8799effb3c00ffe8ef`
    )
    return { weather }
  },
  data() {
    return {
      city: 'Bekasi',
      weather: {},
      weatherAppId: 'fe848d92ce456b8799effb3c00ffe8ef',
    }
  },
  methods: {
    async getWeatherInfo() {
      if (this.city) {
        await this.$axios
          .$get(
            `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.weatherAppId}`
          )
          .then((res) => {
            this.weather = res
          })
      }
    },
    temp() {
      return Math.round(this.weather.main.temp - 273)
    },
  },
}
</script>
