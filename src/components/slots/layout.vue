<template>
  <div>
    <div class="header">
      <slot name='header'></slot>
    </div>
    <div class="content">
      <slot></slot>
    </div>
    <div class='footer'>
      <slot name='footer' :fc="footerContent"></slot>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        remark: [
          '好好学习，天天向上周一',
          '好好学习，天天向上周二',
          '好好学习，天天向上周三',
          '好好学习，天天向上周四',
          '好好学习，天天向上周五',
          '好好学习，天天向上周六',
          '好好学习，天天向上周日'
        ]
      }
    },
    computed: {
      footerContent() {
        return this.remark[new Date().getDay()-1]
      }
    }
  }
</script>
<style scoped>
.header{
  height:60px;
  background:#f00;
}
.content{
  height:300px;
  background:#ff0;
}
.footer{
  height:60px;
  background:#0f0;
}
</style>