<template>
  <div class="col card text-center p-3">
    <div class="col p-3">
      <img :src="discSrc" :alt="discTitle" class="img-fluid" />
      <h1 class="text-white pt-3 fs-3">{{ discTitle }}</h1>
      <h2 class="fs-4 pt-3">{{ discAuthor }}</h2>
      <h3 class="fs-5">{{ discYear }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardDisco",
  props: {
    discAuthor: String,
    discYear: String,
    discTitle: String,
    discSrc: String,
  },
};
</script>

<style scoped  lang="scss">
@import "../assets/temporary/variables";

.card {
  background-color: transparent;
  border: none;

  div {
    background-color: $greydark;
  }
}

h1 {
  font-weight: bolder;
}

h2,
h3 {
  color: grey;
  font-weight: unset;
}
</style>
