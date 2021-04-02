<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Form @submit="handleSubmit">
    <Checkbox name="isPizza" :value="true" />

    <button class="" type="submit">Submit</button>
  </Form>
</template>

<script>
import { Form } from "vee-validate"
import Checkbox from "./components/Checkbox.vue"

export default {
  name: "App",
  components: {
    Checkbox,
    Form,
  },
  setup() {
    const handleSubmit = (values) => {
      values.isPizza = !!values.isPizza
      console.log(values)
    }
    return { handleSubmit }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
