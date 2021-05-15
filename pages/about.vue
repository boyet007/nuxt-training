<template>
  <div><h1>About</h1></div>
</template>

<script>
export default {
  // load before mount
  asyncData() {
    return { title: 'About' }
  },
  head() {
    return {
      title: 'About',
      script: [{ src: '/about.js' }],
    }
  },
}
</script>
