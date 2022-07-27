<template>
  <div class="character">
    <img :src="character.image" alt="imageCharacter" />
    <div class="character_info">
      <h3>{{ character.name }}</h3>
      <div class="status">
        <span
          :class="
            character.status == 'Alive'
              ? 'VIVO'
              : character.status == 'Dead'
              ? 'MUERTO'
              : 'default'
          "
        ></span>
        <span>{{ character.status }}</span> -
        <span>{{ character.species }}</span>
      </div>
      <div class="origin">
        {{ character.origin.name }}
      </div>
      <div class="location">
        {{ character.location.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["character"],
};
</script>

<style>
</style>