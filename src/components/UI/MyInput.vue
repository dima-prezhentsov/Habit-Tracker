<template>
  <input type="text" class="input" placeholder="name" :value="modelValue" @input="updateValue">
</template>

<script>
export default {
  name: "MyInput",
  props: {
    modelValue: [String]
  },

  methods: {
    updateValue(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  border-radius: 25px;
  padding: 20px 15px;
  font-size: 1.5em;
  margin-top: 10px;
}
</style>