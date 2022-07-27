<template>
  <div class="search">
    <input
      type="text"
      placeholder="Busca tu pj"
      v-model="name"
      @keyup="filter()"
    />
  </div>
</template>

<script>
import { ref } from "vue";
import { useStore } from "vuex";
export default {
  setup() {
    const store = useStore();
    const name = ref("");

    const filter = () => {
      store.dispatch("filterByName", name.value);
    };

    return {
      name,
      filter,
    };
  },
};
</script>

<style>
</style>