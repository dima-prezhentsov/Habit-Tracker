<template>
  <input type="text" class="input" placeholder="name" :value="modelValue" @input="updateValue">
</template>

<script>
/**
 * UI component Input*/
export default {
  name: "MyInput",
  props: {
    modelValue: [String]
  },

  methods: {
    /** this method update input value
     * @param {event} event*/
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