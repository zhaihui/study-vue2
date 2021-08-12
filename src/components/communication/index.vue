<template>
  <div>
    <Child1 msg="some msg from parent" @some-event="onSomeEvent"/>
    <Child2 msg="some msg from parent" @click='onClick' />
    <button @click='goHome'>回家吃饭</button>
  </div>
</template>
<script>
  import Child1 from './Child1.vue'
  import Child2 from './Child2.vue'
  export default {
    components: {
      Child1,
      Child2
    },
    methods: {
      onSomeEvent(msg){
        console.log('Communition: ', msg)
      },
      goHome(){
        //直接访问 第一个子组件的eat方法
        // console.log(this.$children)
        this.$children[0].eat()
        this.$children[1].eat()
      },
      onClick() {
        console.log('来自父组件的回调函数处理', this)
      }
    },
  }
</script>
<style scoped>

</style>