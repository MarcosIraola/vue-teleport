<script setup>
import Popup from './components/Popup.vue'
</script>

<template>

  <h1>Hola</h1>
  <Teleport to="#portal-target">
    <Popup ref="popup" :title="'Pop up test'" :sub="'Marcos blabla'">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusamus repellat itaque totam explicabo odit nemo voluptatum, non magnam eos voluptatem cum voluptatibus qui nulla fugiat dolor vero, dolorum amet at.
    </Popup>
  </Teleport>
  <button class="btn" @click="$refs.popup.show = !$refs.popup.show">
    Open Modal
  </button>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
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
}
</style>
