<template>
  <label :for="props.name">
    {{ checked ? "checked" : "unchecked" }}
    <input
      :id="props.name"
      :name="props.name"
      type="checkbox"
      @change="handleChange(props.value)"
    />
  </label>
</template>

<script>
import { useField } from "vee-validate"

export default {
  props: {
    name: String,
    value: {
      type: Boolean,
    },
  },
  setup(props) {
    const { checked, handleChange } = useField(
      "isPizza",
      {},
      {
        type: "checkbox",
        valueProp: props.value,
      }
    )

    console.log(props)

    return { props, checked, handleChange }
  },
}
</script>

<style>
</style>