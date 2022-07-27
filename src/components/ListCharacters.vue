<template>
  <section>
    <div class="characters">
      <div
        class="characters_item"
        v-for="character in characters"
        :key="character.id"
      >
        <cardCharacter :character="character" />
      </div>
    </div>
  </section>
</template>

<script>
import { onMounted, computed } from "vue";
import { useStore } from "vuex";
import cardCharacter from "@/components/cardCharacter";
export default {
  components: {
    cardCharacter,
  },
  setup() {
    const store = useStore();
    const characters = computed(() => {
      return store.state.charactersFilter;
    });

    onMounted(() => {
      store.dispatch("getCharacters");
    });

    return {
      characters,
    };
  },
};
</script>

<style>
</style>