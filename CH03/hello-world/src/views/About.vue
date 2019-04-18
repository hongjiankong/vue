<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{msg}}</p>
  </div>
</template>
<script>
import st from "@/store";
export default {
  name: "about",
  st,
  data () {
    return { msg: st.state.count };
  }
};
</script>