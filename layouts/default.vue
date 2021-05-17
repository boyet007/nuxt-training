<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-toolbar color="#3F51B5" dark>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Learning Nuxt</v-toolbar-title>

        <v-spacer></v-spacer>
        <v-btn text href="/weather-app"> Weather </v-btn>
      </v-toolbar>
    </v-flex>
    <v-main>
      <nuxt />
    </v-main>
  </v-layout>
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
