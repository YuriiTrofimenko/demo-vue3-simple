<template lang='pug'>
.counter(@click="increase") {{state.count}}
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'Counter',
  props: {
    initialCount: Number
  },
  setup (props) {
    const state = reactive({
      count: props.initialCount
    })
    function increase () {
      state.count++
    }
    return {increase, state}
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
