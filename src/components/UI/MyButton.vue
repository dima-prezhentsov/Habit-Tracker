<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "MyButton"
}
</script>

<style scoped>

.btn {
  margin-top: 86px;
  background: #FFFFFF;
  border: 1px solid #5DD39E;
  border-radius: 50px;
  font-weight: 600;
  font-size: 32px;
  color: #5DD39E;
  line-height: 44px;
  padding: 10px 15px;
  width: 25vw;
  min-width: 150px;
  transition: 0.5s;
}

.btn:hover {
  background: #5DD39E;
  color: #FFFFFF;
  transition: .5s;
}

</style>