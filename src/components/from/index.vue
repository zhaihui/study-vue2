<template>
  <div id="app">
    <KFrom :model='userInfo' :rules="rules" ref='loginForm'>
      <KFromItem label='用户名' prop='username'>
        <KInput v-model="userInfo.username" placeholder='请输入用户名称'></KInput>
      </KFromItem>
      <KFromItem label='密码' prop='password'>
        <KInput v-model="userInfo.password" type="password"></KInput>
      </KFromItem>
      <KFromItem>
        <button @click="login">登录</button>
      </KFromItem>
    </KFrom>
  </div>
</template>

<script>
import KFrom from '@/components/from/KFrom.vue'
import KFromItem from '@/components/from/KFromItem.vue'
import KInput from '@/components/from/KInput.vue'
export default {
  name: 'From',
  components: {
    KFrom,
    KFromItem,
    KInput
  },
  data() {
    return {
      userInfo: {
        username:'tom',
        password: ''
      },
      rules: {
        username: [{required: true, message: '请输入用户名称'}],
        password: [{required: true, message: '请输入密码'}]
      }
    }
  },
  methods: {
    login() {
      this.$refs['loginForm'].validate(valid => {
        if(valid) {
          alert('submit')
        } else {
          console.log('error submit')
          return false
        }
      })
    }
  },
}
</script>

<style scoped>

</style>
