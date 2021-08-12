<template>
  <div>
    <h2>插槽</h2>
    <Layout>
      <!-- 具名插槽 -->
      <template v-slot:header>全栈工程师</template>
      <!-- 匿名插槽 -->
      <template>content...</template>
      <!-- 作用域插槽 (数据来自子组件) {fc} 这是解构语法，可能有多个值-->
      <template v-slot:footer="{fc}">{{fc}}</template>
    </Layout>
  </div>
</template>
<script>
  import Layout from './layout.vue'
  export default {
    components:{
      Layout
    },
    mounted() {
      console.log('this====', this.fc)
    },
  }
</script>
<style scoped>

</style>