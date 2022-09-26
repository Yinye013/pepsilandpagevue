<template>
  <div class="hero-section">
    <div class="left">
      <h1 class="heading-primary">That's What<br />I Like!</h1>
      <p class="description">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque a libero
        neque, possimus delectus doloribus vitae nemo maiores recusandae
        eligendi ab quasi dignissimos. At quod veniam nulla consequuntur quam
        consequuntur! Necessitatibus, culpa!
      </p>
      <a href="/">View All Products</a>
    </div>

    <div class="right">
      <img :src="src" alt="Pepsi001" ref="heroCan" />
    </div>
  </div>

  <the-footer :img="images" @toggle-can="changeCan"></the-footer>
</template>

<script>
import TheFooter from "./TheFooter.vue";
export default {
  components: {
    TheFooter,
  },
  data() {
    return {
      src: "/images/pepsi001.png",
      images: [
        { src: "/images/pepsi001.png", alt: "Pepsi001", color: "#0062be" },
        { src: "/images/pepsi002.png", alt: "Pepsi002", color: "#e60c2c" },
        { src: "/images/pepsi003.png", alt: "Pepsi003", color: "#1e1e1e" },
      ],
    };
  },
  methods: {
    changeCan(img, color) {
      //when passing in the emitted component the parameters are passed again here
      this.src = img;
      document.body.style.background = color;
      // console.log(document.body);
    },
  },
};
</script>

<style scoped>
.hero-section {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  max-width: 120rem;
  margin: 0 auto;
  column-gap: 4.8rem;
}
.heading-primary {
  margin-top: 5.2rem;
  margin-bottom: 2rem;
  color: #fff;
  text-transform: uppercase;
  font-size: 6.2rem;
  letter-spacing: normalize;
  margin-bottom: 3rem;
  font-weight: 800;
}

.description {
  color: #fff;
  letter-spacing: 1.1;
  line-height: 1.5;
  font-size: 1.8rem;
  margin-bottom: 3rem;
}
.right {
  display: grid;
  justify-items: center;
}

a:link,
a:visited {
  display: inline-block;
  background-color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  color: #000;
  padding: 1.6rem 3.2rem;
  border-radius: 100px;
  font-size: 1.8rem;
  font-weight: 700;
}
@media screen and (max-width: 75em) {
  /* landscape tablets */
  .right img {
    width: 40%;
  }
}
@media screen and (max-width: 48em) {
  /* portrait tablets */
  .hero-section {
    display: grid;
    grid-template-columns: 1fr;
    gap: 4rem;
    text-align: center;
    margin-bottom: 3rem;
  }
  .right {
    grid-row: 1;
  }
  .right img {
    width: 30%;
  }
}
@media screen and (max-width: 34em) {
  /* portrait tablets */
  .hero-section {
    padding: 0 1.5rem;
  }
}
</style>
