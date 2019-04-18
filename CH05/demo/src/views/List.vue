<template>
  <div>
    <div v-for="(item, index) in list" :key="index">{{item.title}}</div>
  </div>
</template>
<script>
import store from "@/store";
export default {
  name: "list",
  store,

  computed: {
    list() {
      return store.state.list;
    }
  }
};
</script>
<style scoped>
</style>
