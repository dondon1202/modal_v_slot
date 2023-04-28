<script>
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import MoDal from './components/MoDal.vue'
export default {
  data() {
    return {
      title: '',
      content: ''
    }
  },
  components: {
    MoDal
  },
  methods: {
    setShowModal(value) {
      if (value === 'right') {
        this.title = 'RIGHT BTN'
        this.content = '往右走'
      } else {
        this.title = 'LEFT BTN'
        this.content = '往左走'
      }
    }
  }
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
      <button
        type="button"
        class="btn btn-primary"
        data-bs-toggle="modal"
        data-bs-target="#exampleModal"
        @click="this.setShowModal('left')"
      >
        LEFT
      </button>
      <button
        type="button"
        class="btn btn-primary"
        data-bs-toggle="modal"
        data-bs-target="#exampleModal"
        @click="this.setShowModal('right')"
      >
        RIGHT
      </button>
    </div>
    <div class="">
      <mo-dal>
        <template v-slot:title>{{ this.title }}</template>
        <template v-slot:content>{{ this.content }}</template>
      </mo-dal>
    </div>
  </header>

  <!-- <RouterView /> -->
</template>

<style scoped>
.btn {
  margin: 10px;
  width: 80px;
}
header {
  line-height: 1.5;
  max-height: 100vh;
  justify-content: space-between;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
