<template>
  <div class="container mx-auto bg-white">
    <div class="col-span-12">
      <MenuComponent />
    </div>
    <div class="col-span-12">
      <HeroComponent />
    </div>
  </div>
</template>

<script>
import HeroComponent from './components/HeroComponent.vue'
import MenuComponent from './components/MenuComponent.vue'
export default {
  name: 'App',
  components: {
    MenuComponent,
    HeroComponent,
  },
}
</script>

<style></style>
