<template>
  <div>
    <h1>About</h1>
    <NLink to="/">Home</NLink>
  </div>
</template>

<script>
export default {
  // load before mount

  asyncData() {
    return { title: 'About' }
  },
  fetch() {},
  head() {
    return {
      title: 'About',
      script: [{ src: '/about.js' }],
    }
  },
}
</script>
