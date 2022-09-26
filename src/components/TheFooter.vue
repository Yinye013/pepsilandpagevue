<template>
  <footer>
    <!-- <img src="../images/pepsi001.png" alt="Pepsi001" ref="pepsiBlue" />
    <img
      src="../images/pepsi002.png"
      alt="Pepsi002"
      ref="pepsiWhite"
      @click="toggleImage"
    />
    <img src="../images/pepsi003.png" alt="Pepsi003" ref="pepsiBlack" /> -->
    <img
      v-for="image in img"
      :src="image.src"
      :alt="image.alt"
      @click="switchCan(image.src, image.color)"
    />
  </footer>
</template>

<script>
export default {
  data() {
    return {};
  },
  // emits: {
  //   "toggle-can": function (img) {
  //     if (img) {
  //       return true;
  //     }
  //   },
  // },
  props: ["img"],
  methods: {
    switchCan(img, color) {
      this.$emit("toggle-can", img, color);
      // console.log(color);
    },
  },

  emits: ["toggle-can"],
};
</script>

<style scoped>
footer {
  display: flex;
  justify-content: center;
  max-width: 120rem;
  margin: 0 auto;
  gap: 6rem;
  /* flex-direction: row; */
  /* padding-bottom: 1.5rem; */
}
footer img {
  height: 11rem;
  cursor: pointer;
  transition: all 0.3s;
}
footer img:hover,
footer img:active {
  transform: translateY(-15px);
}
</style>
