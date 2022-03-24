<template>
  <main>
    <div class="container overflow hidden">
      <div class="row row-cols-5 gx-4">
        <CardDisco
          v-for="disco in arrDisco"
          :key="disco.title"
          :discSrc="disco.poster"
          :discTitle="disco.title"
          :discAuthor="disco.author"
          :discYear="disco.year"
        />
      </div>
    </div>
  </main>
</template>


<script>
import CardDisco from "./CardDisco.vue";
import axios from "axios";

export default {
  name: "MainDI",
  data() {
    return {
      arrDisco: null,
    };
  },

  components: {
    CardDisco,
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.arrDisco = response.data.response;
        console.log(this.arrDisco);
      });
  },
};
</script>

<style scoped lang="scss">
@import "../assets/temporary/variables";

main {
}
</style>
