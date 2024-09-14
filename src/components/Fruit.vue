<template>
  <li>{{ name }}?!</li>
</template>


<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    }
  },
  // created() {
  //   console.log('Fruit Created!')
  // },
  // mounted() {
  //   console.log('Fruit Mounted!')
  // }  
}
</script>

<style scoped lang="scss">
h1 {
  color: red !important;
}
</style>
