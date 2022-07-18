<script>
import HeaderComp from "./components/Template/HeaderComp.vue";
import FooterComp from "./components/Template/FooterComp.vue";
export default {
  components: { HeaderComp, FooterComp },
};
</script>

<template>
  <HeaderComp />
  <main><RouterView /></main>
  <FooterComp />
</template>

<style>
@import "@/assets/base.css";

#app {
  max-width: 1280px;
  margin: 0 auto;
  /* padding: 2rem; */
  height: 100vh;

  font-weight: normal;
}

.conteudo {
  border: 1px solid black;
  width: 100px;
  height: 30px;
  overflow: scroll;
}

main {
  min-height: 70%;
}
</style>
