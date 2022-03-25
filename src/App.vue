<template>
  <div id="app">
    <HeaderDI @ricerca="genreString" />
    <MainDI :genreChosen="optionGenre" />
    <FooterDI />
  </div>
</template>

<script>
import HeaderDI from "./components/HeaderDI.vue";
import MainDI from "./components/MainDI.vue";
import FooterDI from "./components/FooterDI.vue";

export default {
  name: "App",
  components: {
    HeaderDI,
    MainDI,
    FooterDI,
  },

  data() {
    return {
      optionGenre: "",
    };
  },

  methods: {
    genreString(genre) {
      this.optionGenre = genre;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "./assets/style";

#app {
  background-color: $darkblue;
}
</style>
