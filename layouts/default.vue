<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-toolbar
        dark
        src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Learning Nuxt</v-toolbar-title>

        <v-spacer></v-spacer>
        <v-btn text href="/"> Home </v-btn>
        <v-btn text href="/about"> About </v-btn>
        <v-btn text href="/inspire"> Inspire </v-btn>
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
    return {
      title: 'I am default layout',
    }
  },
}
</script>
