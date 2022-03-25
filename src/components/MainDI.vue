<template>
  <main>
    <div class="container overflow hidden">
      <div class="row row-cols-5 gx-4">
        <CardDisco
          v-for="disco in genreFiltered"
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
  props: {
    genreChosen: String,
  },

  data() {
    return {
      arrDisco: [],
    };
  },

  components: {
    CardDisco,
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.arrDisco = response.data.response.map((disco) => ({
          title: disco.title,
          poster: disco.poster,
          author: disco.author,
          year: disco.year,
          genre: disco.genre,
        }));
      });
  },

  computed: {
    genreFiltered() {
      return this.arrDisco.filter((objDisco) =>
        objDisco.genre.toLowerCase().includes(this.genreChosen.toLowerCase())
      );
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/temporary/variables";

main {
}
</style>
