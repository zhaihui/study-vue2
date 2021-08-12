<template>
  <div @click="$emit('some-event', 'msg-from-child1')">
    <h3>Child1</h3>
    <p>{{msg}}</p>
  </div>
</template>
<script>
  export default {
    props:{
      msg: {
        type: String,
        default: ''
      }
    },
    mounted() {
      // this.$bus.$on('event-from-child2', msg => {
      //   console.log('Child1: ', msg)
      // })
      this.$parent.$on('event-from-child2', msg => {
        console.log('Child1: ', msg)
      })
    },
    methods: {
      eat(){
        console.log('communication 叫Child1回家吃饭')
      }
    },
  }
</script>
<style scoped>

</style>