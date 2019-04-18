<template>
  <div>
    <form v-if="!isReg">
      <p>用户名</p>
      <input type="text" v-model="name">
      <p>密码</p>
      <input type="password" v-model="password">
      <button type="button" @click="login()">登录</button>
      <button type="button" @click="reg()">注册</button>
    </form>

    <form v-else>
      <p>用户名</p>
      <input type="text" v-model="name">
      <p>密码</p>
      <input type="password" v-model="password">
      <p>确认密码</p>
      <input type="password" v-model="repeat">
      <button type="button" @click="addUser()">确定</button>
      <button type="button" @click="cancel()">取消</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "login",
  data() {
    return {
      isReg: false,
      name: "",
      password: "",
      repeat: ""
    };
  },
  methods: {
    login() {
      if(this.name===localStorage.getItem('name')&& this.password===localStorage.getItem('password')){
        this.$router.push("/home/list");
      }else{
        this.name='';
        this.password='';
        this.repeat='';
        alert("用户名密码不正确")
      }
    },
    reg() {
      this.isReg = true;
    },
    addUser() {
      if (this.password === this.repeat) {
        localStorage.setItem("name", this.name);
        localStorage.setItem("password", this.password);
        this.name='';
        this.password='';
        this.repeat='';
        this.isReg=false

      } else {
        alert("两次密码不一致");
      }
      // this.isReg = true;
    },
    cancel() {
      this.isReg = false;
    }
  }
};
</script>