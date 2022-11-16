<template>
<div v-if="habits.length > 0">
  <habit-item
      v-for="habit in habits"
      :key="habit.id"
      :habit="habit"
      @openDialog="opendDialog"
  >

  </habit-item>
</div>
  <div v-else>Habit list is empty</div>
</template>

<script>
import HabitItem from "@/components/HabitItem";
export default {
  name: "HabitList",
  components: {HabitItem},
  props: {
    habits: {
      type: Array,
      required: true,
    }
  },
  methods: {
    opendDialog(habit) {
      this.$emit('openDialog', habit)
    }
  }
}
</script>

<style scoped>

</style>