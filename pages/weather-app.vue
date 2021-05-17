<template>
  <v-container>
    <v-flex xs12>
      <h1 class="text-center">Weather App</h1>
    </v-flex>

    <v-flex xs12>
      <v-card color="blue-grey darken-2" dark>
        <v-card-text>Here card</v-card-text>
      </v-card>
    </v-flex>
    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo()">
        <v-text-field
          v-model="city"
          label="Enter City Name"
          solo
        ></v-text-field>
      </v-form>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: 'London',
      api: 'fe848d92ce456b8799effb3c00ffe8ef',
      weather: {},
    }
  },
  created() {
    this.getWeatherInfo()
  },
  methods: {
    getWeatherInfo() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.api}`
        )
        .then((res) => (this.weather = res))
    },
  },
}
</script>
