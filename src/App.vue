<template>
  <HeaderComponent />
  <main class="mt-5">
    <CharacterList />
    <!-- <button @click="nextPage">Next Page</button>
    <button @click="prevPage">Prev Page</button> -->
  </main>
</template>

<script>
import { store } from "./data/store";
import axios from "axios";
import HeaderComponent from "./components/HeaderComponent.vue";
import CharacterList from "./components/CharacterList.vue";
export default {
  name: "App",
  components: {
    HeaderComponent,
    CharacterList,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCharacters() {
      const url = store.baseUrl;
      const options = {
        params: {
          num: store.params.num,
          offset: store.params.offset,
        },
      };
      axios.get(url, options).then((res) => {
        store.characterList = res.data.data;
      });
    },
    // nextPage() {
    //   store.params.num += 50;
    //   store.params.offset += 50;
    //   const url = store.baseUrl;
    //   const options = {
    //     params: {
    //       num: store.params.num,
    //       offset: store.params.offset,
    //     },
    //   };
    //   axios.get(url, options).then((res) => {
    //     store.characterList = res.data.data;
    //   });
    // },
    // prevPage() {
    //   store.params.num -= 50;
    //   store.params.offset -= 50;
    //   const url = store.baseUrl;
    //   const options = {
    //     params: {
    //       num: store.params.num,
    //       offset: store.params.offset,
    //     },
    //   };
    //   axios.get(url, options).then((res) => {
    //     store.characterList = res.data.data;
    //   });
    // },
  },
  mounted() {
    this.getCharacters();
  },
};
</script>

<style lang="scss" scoped></style>
