<template>
  <section class="container">
    <div class="row">
      <CardComponent
        v-for="(character, index) in store.characterList"
        :key="character.id"
        :character="character"
      />
    </div>
  </section>
</template>

<script>
import { store } from "../data/store";
import CardComponent from "./CardComponent.vue";
export default {
  name: "CharacterList",
  components: {
    CardComponent,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped></style>
