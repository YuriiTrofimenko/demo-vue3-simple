<template lang='pug'>
.counter(@click="increase" ref='counterRef') {{state.count}}
</template>

<script>
import { reactive, ref, onMounted } from 'vue'
export default {
  name: 'Counter',
  props: {
    initialCount: Number
  },
  setup (props) {
    const counterRef = ref(null)
    const state = reactive({
      count: props.initialCount
    })
    function increase () {
      state.count++
    }
    onMounted(() => {
      setInterval(() => {console.log(counterRef.value.innerText)}, 4000)
    })
    return {increase, state, counterRef}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang='stylus'>
.counter
  color darkred
  font-size 48px
  font-family 'Times New Roman', Times, serif
</style>
