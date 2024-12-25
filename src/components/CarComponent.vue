<template>
  <div>
    <h1>Car Component</h1>
    <p>This is a car component</p>
    <p>Brand: {{ brand }}</p>
    <p>Model: {{ model }}</p>
    <p>Color:</p>
    <ul>
      <li v-for="(color, index) in colors" :key="index">{{ index + 1 + '. ' + color }}</li>
    </ul>
    <p>Price: {{ price }}</p>
    <p>Power: {{ power }}</p>
    <button @click="upPower(index)">Up Power</button>
    <button @click="$emit('downPower')">Down Power</button>

    <p>Message: {{ message.title }} - {{ message.body }}</p>
    <div>
      <p>contado: {{ count }}</p>
      <button @click="increment">Incrementar</button>
    </div>
    <TestComponent />
  </div>
</template>

<script>
import TestComponent from './TestComponent.vue'
import { ref } from 'vue'

export default {
  props: {
    brand: String,
    model: String,
    colors: Array,
    price: Number,
    power: String,
    message: Object,
    upPower: Function,
  },
  emits: ['downPower'],

  components: {
    TestComponent,
  },
  setup(props) {
    const count = ref(0)
    const increment = () => {
      count.value++
    }
    console.log(props.power)
    return {
      count,
      increment,
    }
  },
}
</script>

<style scoped>
h1 {
  color: red;
}
p {
  color: blue;
}
button {
  background-color: green;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
</style>
