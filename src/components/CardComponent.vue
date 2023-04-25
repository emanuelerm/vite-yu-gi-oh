<template>
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    <div class="character text-center">
      <img
        v-for="characterImg in character.card_images"
        :src="characterImg.image_url"
        alt=""
      />
      <h4>{{ character.name }}</h4>
      <h5>{{ character.archetype }}</h5>
      <p>{{ character.desc }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: ["character"],
};
</script>

<style lang="scss" scoped>
.character {
  width: fit-content;
  img {
    width: 100%;
    height: auto;
  }
}
</style>
