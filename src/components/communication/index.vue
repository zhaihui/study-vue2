<template>
  <div>
    <Child1 msg="some msg from parent" @some-event="onSomeEvent"/>
    <Child2 />
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
    data() {
      
    },
    methods: {
      onSomeEvent(){
        
      }
    },
  }
</script>
<style scoped>

</style>