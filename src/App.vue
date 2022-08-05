<template>
  <div>
    <header1 @menu="cambiarMenu" />
    <div v-if="pageSelected == 1">
      <FilterByStatus />
      <FilterByName />
      <ListCharacters />
    </div>
    <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import ListCharacters from "@/components/ListCharacters";
import FilterByStatus from "@/components/FilterByStatus";
import FilterByName from "@/components/FilterByName";
import header1 from "@/components/Header.vue";
export default {
  name: "App",
  components: {
    ListCharacters,
    FilterByStatus,
    FilterByName,
    header1,
    // HelloWorld,
  },
  data() {
    return {
      pageSelected: 0,
    }
  },
  methods: {
    cambiarMenu(page) {
      this.pageSelected = page;
    }
  },
};
</script>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
