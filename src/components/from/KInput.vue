<template>
  <div>
    <input :type="type" :value="value" @input="onInput" v-bind='$attrs'>
  </div>
</template>
<script>
  export default {
    inheritAttrs: false, // 避免吧attrs设置到根元素上
    props: {
      value: {
        type: String,
        default: ''
      },
      type: {
        type: String,
        default: 'text'
      }
    },
    methods: {
      onInput(e) {
        this.$emit('input', e.target.value)
        // 通知父组件执行校验
        this.$parent.$emit('validate')
      }
    },
  }
</script>
<style scoped>

</style>