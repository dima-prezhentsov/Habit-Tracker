<template>
  <div class="item">
    <p>{{ habit.name }}</p>
  </div>
</template>

<script>
/** Habit Item component*/
export default {
  name: "HabitItem",
  props: {
    habit: {
      type: Object,
      required: true
    }
  },
  methods: {
    /**
     * Gets called when the user click on the habit
     */
    openDialog(habit) {
      this.$emit('openDialog', habit)
    }
  }
}
</script>

<style scoped lang="scss">
.item {
  height: 90px;
  width: 30vw;
  min-width: 300px;
  border-radius: 50px;
  background: #BCE784;
  display: flex;
  align-items: center;
  margin-top: 20px;
  padding-left: 30px;
  font-weight: 300;
  font-size: 32px;
  line-height: 44px;
  color: #FFFFFF;
  transition: .5s;
  img {
    margin-left: auto;
    margin-right: 20px;
    transition: .5s;
  }
  img:hover {
    transform: rotate(180deg);
    transition: .5s;
  }
}

.item:hover {
  background-color: #b1e078;
  transition: .3s;
}

</style>