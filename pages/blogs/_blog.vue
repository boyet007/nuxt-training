<template>
  <div>
    I am a blog post
    <h2>{{ slug.blog }}</h2>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    // untuk validasi kalau param harus berupa angka
    return /^\d+$/.test(params.blog)
  },
  data() {
    return {
      slug: this.$route.params,
    }
  },
  created() {
    // console.log(this.$route.params)
  },
}
</script>
