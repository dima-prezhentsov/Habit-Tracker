<template>
  <form class="create_form" @submit.prevent>
    <my-input type="text" class="input" placeholder="description" v-model="habit.description"></my-input>
<!--    <my-input type="text" class="input" placeholder="month" v-model="habit.month"></my-input>-->
    <my-button @click="createHabit">Ok</my-button>
  </form>
</template>

<script>
export default {
  name: "CreatingFrom",
  data() {
    return {
      habit: {
        id: '',
        description: '',
        month: '',
      },
    }
  },
  methods: {
    createHabit() {
      this.habit.id = Date.now()
      this.$emit('create', this.habit)
      this.habit = {
        description: '',
        month: '',
      }
    }
  }
}
</script>

<style scoped>
.create_form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>