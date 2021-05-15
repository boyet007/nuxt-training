<template>
  <div>{{ error.message }}</div>
</template>

<script>
export default {
  layout: 'errorLayout',
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
}
</script>
