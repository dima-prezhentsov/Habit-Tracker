<template>
  <div class="navbar">
    <h1 class="navbar_text">HABIT TRACKER</h1>
  </div>
  <div class="container">
    <my-button
        @click="creatingDialogVisible = true"
    >
      Create habit
    </my-button>

    <my-dialog v-model:show="creatingDialogVisible">
      <creating-from
          @create="createHabit"
      >
      </creating-from>
    </my-dialog>


    <habit-tracker
        @remove="deleteHabit"
        :habits="habits"
    >

    </habit-tracker>

  </div>
</template>

<script>

import HabitTracker from "@/components/HabitTracker";
import CreatingFrom from "@/components/CreatingFrom";
export default {
  name: 'App',
  components: {
    HabitTracker,
    CreatingFrom
  },

  data() {
    return {
      habits: [
        {id: 1,description: 'Lorem ipsum dolor sit.', month: 'Jan'},
        {id: 2,description: 'Deserunt dicta odit repudiandae', month: 'Jan'},
        {id: 3,description: 'Molestiae omnis praesentium voluptatibus', month: 'Jan'},
      ],
      creatingDialogVisible: false,
      openingDialogVisible: false,
    }
  },
  methods: {
    createHabit(habit) {
      this.habits.push(habit)
      this.creatingDialogVisible = false
    },
    deleteHabit(habit) {
      this.habits = this.habits.filter(h => h.id !== habit.id)
    }
  }
}
</script>

<style lang="scss">

body {
  margin: 0;
  padding: 0;
}

* {
  box-sizing: border-box;
}

h1,h2,h3,p {
  margin: 0;
}

a {
  text-decoration: none;
  outline: none;
}
#app {
  font-family: Open Sans;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.navbar {
  width: 100%;
  height: 130px;
  background: #5DD39E;
  display: flex;
  align-items: center;
  justify-content: center;
}

.navbar_text {
  font-weight: 400;
  font-size: 6vmin;
  line-height: 131px;
  color: #FFFFFF;

  text-shadow: 6px 6px 4px rgba(0, 0, 0, 0.25);
}

.container {
  margin: 0 auto;
  min-height: 10em;
  width: 90vw;
}





</style>
