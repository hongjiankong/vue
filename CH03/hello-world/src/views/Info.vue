<template>
  <div>
    <p>Hello Vue Component</p>

    <button type="button" @click="add()">Click Me</button>
  </div>
</template>
<script>
import store from "@/store";
export default {
  name: "info",
  store,
  methods: {
    add :function() {
      console.log("add event!!!");
      store.commit("Increase");
    }
  }
};
</script>