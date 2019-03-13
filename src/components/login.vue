<template>
  
    <div class="container">
    <x-header :left-options="{showBack: true}">This is the page title.</x-header>
    <group title="用户登录">
      <x-input title="手机号码" mask="999 9999 9999" v-model="phone"></x-input>
       <x-input title="密码" type="password" v-model="password"></x-input>
    </group>
    <div class="btn">
      <x-button @click.native="login">登录</x-button>>
  </div>
</template>

<script>
import { AlertModule, Group, Cell, XInput, XButton, Aler, XHeader } from 'vux'
                            
export default {
  components: {
    Group,
    Cell,
    XButton,
    XInput,
    AlertModule,
    Aler,
    XHeader
  },
methods: {
  login() {
    if(this.password === '123456'){
      this.router.push({ path: '/'})
    }else{AlertModule.show({
      title: "登陆失败",
      content: "密码错误"
    })
      
    }
  }
}
}
</script>

<style>
.vux-demo {
  text-align: center;
}
.logo {
  width: 100px;
  height: 100px
}
</style>
