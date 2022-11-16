<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "MyLittleButton"
}
</script>

<style scoped>
.btn {
  font-family: Open Sans;
  background: none;
  border: 1px solid #5DD39E;
  color: #5DD39E;
  border-radius: 5px;
  font-size: 1rem;
  font-weight: 400;
}

.btn:hover {
  background-color: #5DD39E;
  color: #FFFFFF;
  transition: .3s;
}
</style>