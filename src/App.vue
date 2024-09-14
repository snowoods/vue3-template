<template>
  <h1 
    :[attr]="'active'"
    @[event]="add">
    {{ msg }}
  </h1>

  <h1 @click="increase">
    {{ count }}
  </h1>
  <div v-if="count > 4">
    4보다 큽니다.
  </div>
  <div>
    <ul>
      <Fruit 
        v-for="fruit in fruits" 
        :key="fruit"
        :name="fruit">
        {{ fruit }}
      </Fruit>
    </ul>
  </div>
  <HelloWorld />
</template>

<script>
import HelloWorld from '~/components/HelloWorld'
import Fruit from '~/components/Fruit'

export default {
  data() {
    return {
      msg: 'active',
      attr: 'class',
      event: 'click',

      count: 0,
      fruits: ['Apple', 'Banana', 'Cherry']
    }
  },
  components: {
    HelloWorld,
    // Fruit: Fruit // 이름이 같으면 생략 가능
    Fruit
  },  
  methods: {
    add() {
      this.msg += '!'
    },
    increase() {
      this.count += 1
    }
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
  .active {
    color: royalblue;
    font-size: 100px;
  }
  h1 {
    font-size: 50px;
    color: royalblue;
  }
  ul {
    font-size: 40px;
  }
</style>