<template>
  <div>
    <h1>Car Options</h1>
    <p>Brand: {{ brand }}</p>
    <p>Model: {{ model }}</p>
    <p>Color: {{ color }}</p>
    <p>Price: {{ price }}</p>
    <div>
      <p>Power: {{ power }}</p>
      <button @click="encrase">+</button>
      <button @click="decrease">-</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  data() {
    const POWERS = [80, 100, 120, 140, 160]
    let power = ref(POWERS[0])

    const encrase = () => {
      let index = POWERS.indexOf(power.value)
      if (POWERS[index] < POWERS[POWERS.length - 1]) {
        power.value = POWERS[index + 1]
      } else {
        power.value = POWERS[0]
      }
    }
    const decrease = () => {
      let index = POWERS.indexOf(power.value)
      if (POWERS[index] > POWERS[0]) {
        power.value = POWERS[index - 1]
      } else {
        power.value = POWERS[POWERS.length - 1]
      }
    }
    return {
      brand: 'Seat',
      model: 'Ibiza',
      color: ['red', 'blue', 'green'],
      price: 15000,
      power,
      encrase,
      decrease,
    }
  },
}
</script>

<style></style>
