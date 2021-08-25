<template>
  <div>
    <!-- label -->
    <label v-if="label">{{label}}</label>
    <slot></slot>

    <!-- 校验信息 -->
    <p v-if='error'>{{error}}</p>

    <!-- <p>{{from.model}}</p> -->
  </div>
</template>
<script>
  import Schema from 'async-validator'
  export default {
    inject: ['form'],
    data() {
      return {
        error: ''
      }
    },
    props: {
      label: {
        type: String,
        default: ''
      },
      prop: {
        type: String
      }
    },
    mounted() {
      this.$on('validate', () => {
        this.validate()
      })
    },
    methods: {
      validate() {
        //规则 
        // console.log(this.form.rules[this.prop])
        const rules = this.form.rules[this.prop]
        //值
        // console.log(this.form.model[this.prop])
        const value = this.form.model[this.prop]

        //校验描述对象
        const desc = {[this.prop]: rules}
        //创建schema 
        const schema = new Schema(desc)
        return schema.validate({[this.prop]: value}, errors => {
          if (errors) {
            this.error = errors[0].message
          } else {
            this.error = ''
          }
        })
      }
    },
  }
</script>
<style scoped>

</style>