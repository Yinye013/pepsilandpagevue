<template>
  <header>
    <div class="content-header">
      <img src="/images/logo.png" alt="Pepsi Logo" />
    </div>

    <nav :class="{ open: change }" @click="toggleNav">
      <ul>
        <li v-for="lin in navLinks" :key="lin.id">
          <a href="/"> {{ lin.link }}</a>
        </li>
      </ul>
    </nav>
    <div class="toggleNavigation" @click="toggleNav">
      <div class="toggler" :class="{ isToggled: change }"></div>
      <div class="toggler" :class="{ isToggled: change }"></div>
      <div class="toggler" :class="{ isToggled: change }"></div>
      <!-- <p>click me</p> -->
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navLinks: [
        {
          link: "Home",
          id: 1,
        },
        { link: "About", id: 2 },
        { link: "Newsletter", id: 3 },
        { link: "Products", id: 4 },
        { link: "Contact", id: 5 },
      ],
      change: false,
    };
  },
  methods: {
    toggleNav() {
      this.change = !this.change;
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  /* padding: 0.5rem 1rem; */
  justify-content: space-between;
  max-width: 120rem;
  margin: 0 auto;
  margin-bottom: 3.5rem;
}
img {
  margin-top: 1.5rem;
  height: 10rem;
  /* padding-left: 2rem; */
}
nav {
  display: flex;
}
ul {
  list-style: none;
  /* padding: 2rem; */
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5.2rem;
  margin-right: 5rem;
}

a {
  text-decoration: none;
  color: #fff;
  font-size: 2rem;
  cursor: pointer;
}
.toggleNavigation {
  display: none;
}

@media screen and (max-width: 48em) {
  /* portrait tablets */
  .header {
    position: relative;
  }

  nav {
    background-color: #666;

    backdrop-filter: blur(10px);
    position: absolute;
    top: 6rem;
    right: 0.5rem;
    opacity: 0;
    pointer-events: none;
    visibility: 0;
  }
  nav ul {
    color: blanchedalmond;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-right: 0;
    gap: 2rem;
    padding: 0 2rem;
  }
  .open {
    opacity: 1;
  }
  .toggleNavigation {
    display: block;
    /* background-color: orangered; */
    width: 3rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-right: 3rem;
  }
  .toggler {
    width: 2.5rem;
    height: 0.3rem;
    background: #fff;
    margin-bottom: 0.4rem;
    transition: all 0.3s;
  }

  .toggleNavigation .isToggled:nth-child(1) {
    transform: translate(1px, 6px) rotate(45deg);
  }
  .isToggled:nth-child(2) {
    opacity: 0;
  }
  .isToggled:nth-child(3) {
    transform: translate(0px, -6px) rotate(-45deg);
  }
}

@media screen and (max-width: 34em) {
  /* portrait tablets */
  header {
    padding: 0 2rem;
  }
  img {
    height: 7rem;
  }
}
</style>
