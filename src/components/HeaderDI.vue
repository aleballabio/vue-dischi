<template>
  <header class="">
    <div class="container-fluid">
      <div class="row">
        <div class="col d-flex align-items-center pt-3 pb-3">
          <img src="../assets/img/logo-small.svg" alt="Logo" class="logo" />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderDI",
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
