<template>
  <div>
    <p>标题</p>
    <input type="text" v-model="title">
    <p>内容</p>
    <input type="text" v-model="content">
    <hr>
    <button type="button" @click="add()">添加</button>
  </div>
</template>
<script>
import store from "@/store";
export default {
  name: "add",
  store,
  data() {
    return {
      title: "",
      content: ""
    };
  },
  methods: {
    add() {
      var item = { title: this.title, content: this.content };
      store.commit("ADDITEM", item);
      this.title = "";
      this.content = "";
      this.$router.push("/home/list");
    }
  }
};
</script>

<style scoped>
</style>
