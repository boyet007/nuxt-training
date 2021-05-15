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
    <v-container>
      <nuxt />
    </v-container>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
