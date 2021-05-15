<template>
  <div>
    <v-toolbar
      dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Learning Nuxt</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn text><NLink to="/"> Home </NLink> </v-btn>
      <v-btn text><NLink to="/about"> About </NLink> </v-btn>
      <v-btn text><NLink to="/inspire"> Inspire </NLink> </v-btn>
    </v-toolbar>
    <nuxt />
  </div>
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
