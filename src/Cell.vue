<template>
  <div>

    <div id="cell"  v-on:click="onClickSelf">
      <template v-if="a">{{text}}</template>
      <template v-else></template>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  props: ['n'],
  data() {
    return {a: false, text: ''}
  },
  methods: {
    onClickSelf(){
      if(this.text !== ''){return}
      this.a = true
      this.text = this.n % 2 === 0 ? "x" : "o" // 偶数X奇数O
      this.$emit('click', this.text)
    }
  },

}
</script>

<style>
#cell {
  border: 1px solid black;
  width: 100px;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 80px;
}

</style>