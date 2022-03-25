<template>
  <header class="">
    <div class="container-fluid">
      <div class="row">
        <div
          class="
            col
            d-flex
            justify-content-between
            align-items-center
            pt-3
            pb-3
          "
        >
          <img src="../assets/img/logo-small.svg" alt="Logo" class="logo" />
          <div>
            <span class="text-white pe-3">Seleziona Genere:</span>
            <select
              v-model="stringOption"
              @change="$emit('ricerca', stringOption)"
              name="Genre"
              id="selectGenre"
            >
              <option value=""></option>
              <option value="Rock">Rock</option>
              <option value="Pop">Pop</option>
              <option value="Jazz">Jazz</option>
              <option value="Metal">Metal</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderDI",

  data() {
    return {
      stringOption: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/temporary/variables";

header {
  background-color: $greydark;
}

.logo {
  width: 40px;
}
</style>
