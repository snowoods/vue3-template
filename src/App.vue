<template>
  <h1>{{ msg }}</h1>
  <HelloWorld />
</template>

<script>
import HelloWorld from '~/components/HelloWorld'
// import Fruit from '~/components/Fruit'

export default {
  data() {
    return {
      msg: 'active',
    }
  },
  components: {
    HelloWorld,
    // Fruit: Fruit // 이름이 같으면 생략 가능
    // Fruit
  },
  methods: {
  },

  beforeCreate() {
    console.log('Before App Create!', this.count)
  },
  created() {
    console.log('App Created!', this.count)
    console.log(document.querySelector('h1'))
  },
  beforeMount() {
    console.log('Before App Mount!')
    console.log(document.querySelector('h1'))
  },
  mounted() {
    console.log('App Mounted!')
    // 화면에 출력된 데이터를 조회하려면 mounted 훅에서 해야한다.
    console.log(document.querySelector('h1'))
  }
}
</script>

<style lang="scss">
  h1 {
    font-size: 50px;
    color: royalblue;
  }
</style>
