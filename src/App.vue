<template>
  <div>
    <the-header></the-header>
    <the-homepage></the-homepage>
  </div>
</template>
<script>
import TheHeader from "./components/TheHeader.vue";
import TheHomepage from "./components/TheHomepage.vue";

export default {
  components: { TheHeader, TheHomepage },

  methods: {},
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700;800&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  /* background-color: blue; */
  font-family: "Poppins";
}
html {
  font-size: 62.5%;
}
@media screen and (max-width: 84em) {
  html {
    /* padding: 0 3rem; */
  }
}
@media screen and (max-width: 75em) {
  /* landscape tablets */
  html {
    font-size: 56.25%;
  }
}
@media screen and (max-width: 68em) {
  /* landscape tablets */
  html {
    font-size: 56.25%;
    padding: 0 3rem;
  }
}
@media screen and (max-width: 59em) {
  /* portrait tablets */
  html {
    font-size: 50%;
  }
}

@media screen and (max-width: 34em) {
  /* phones */
  /* * {
    max-width: 54.4rem;
    margin: 0 auto;
  } */
}
</style>
