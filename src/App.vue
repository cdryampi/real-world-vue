<template>
  <h1>View JS</h1>
  <br />
  <CarComponent
    :brand="brand"
    :model="model"
    :colors="color"
    :price="price"
    :power="power"
    :message="message"
    :upPower="upPower"
    :getPower="getPower"
    @downPower="downPower"
  />
  <br />
  <CarOptions />
</template>

<script>
import CarComponent from './components/CarComponent.vue'
import CarOptions from './components/CarOptions.vue'
import { ref } from 'vue'

export default {
  components: {
    CarComponent,
    CarOptions,
  },
  setup() {
    let brand = 'Ford'
    let model = 'Mustang'
    let color = ['red', 'blue', 'green']
    let price = 27000
    let powers = [100, 200, 300, 400, 500]
    let power = ref(powers[0])
    let message = {
      title: 'Vue 3',
      body: 'This is a test message',
    }
    const upPower = () => {
      const index = powers.indexOf(power.value)
      if (index < powers.length - 1) {
        power.value = powers[index + 1]
      }
    }
    const downPower = () => {
      const index = powers.indexOf(power.value)
      if (index > 0) {
        power.value = powers[index - 1]
      }
    }

    return {
      brand,
      model,
      color,
      price,
      powers,
      message,
      power,
      upPower,
      downPower,
    }
  },
}
</script>

<style></style>
