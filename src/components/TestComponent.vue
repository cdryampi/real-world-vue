<template>
  <div>
    <h1>Test Component</h1>
    <p>This is a test component</p>
    <div>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="name" />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" />
        </div>
        <div>
          <label for="password">Password:</label>
          <input type="password" id="password" v-model="password" />
        </div>
        <button type="submit">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      password: '',
    }
  },
  methods: {
    submitForm() {
      console.log('Name:', this.name)
      console.log('Email:', this.email)
      console.log('Password:', this.password)
    },
  },
}
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
label {
  font-weight: bold;
}
input {
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
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
