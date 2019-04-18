<template>
  <div>
    <ul>
      <li
        v-for="(item, index) in lists"
        :key="index"
        @click="choose(index)"
        :class="{active:index==currentIndex}"
      >{{item}}</li>
    </ul>

    <button type="button" @click="add()">添加</button>
    <div v-for="(item, index) in addedList" :key="index">{{item}}</div>
  </div>
</template>
<script>
export default {
  name: "demo1",
  data() {
    return {
      lists: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      addedList: [],
      currentIndex: -1
    };
  },
  methods: {
    choose(index) {
      console.log(index);
      this.currentIndex = index;
    },
    add() {
        if(this.currentIndex!==-1){

            this.addedList.push(this.lists[this.currentIndex]);
      this.currentIndex = -1;
        }
    }
  }
};
</script>
<style scoped>
ul {
  list-style: none;
}
li.active {
  background: green;
}
</style>
