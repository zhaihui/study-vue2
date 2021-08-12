<template>
  <div>
    <!-- $listeners 会被展开监听 -->
    <h3 v-on="$listeners">child2</h3>
    <button @click='sendToChild1'>send msg</button>
    <p>{{$attrs.msg}}</p>
  </div>
</template>
<script>
  export default {
    mounted() {
      console.log('-----', this.$listeners)

      
    },
    methods: {
      sendToChild1() {
        // 事件总线
        // this.$bus.$emit('event-from-child2', 'msg-from-child2')
        // $parent
        this.$parent.$emit('event-from-child2', 'msg-from-child2')
      },
      eat(){
        console.log('communication 叫Child2回家吃饭')
      }
    },
  }
</script>
<style scoped>

</style>