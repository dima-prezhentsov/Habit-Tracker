<template>
  <div class="tracker">
    <div class="tracker__header">
      <h3 class="month">month</h3>
      <div class="month__names">
        <h3 class="month__name" 
        :class="{active: activeMonthIndex === index}" 
        @click="activeMonthIndex = index" 
        v-for="(month, index) in monthsEn" 
        :key="month"
        >
          {{ month }}
        </h3>
      </div>
    </div>
    <hr>
    <div class="tracker__inner">
      <div class="habit_item"
             v-for="habit in habits"
             :key="habit.id"
        >
          <my-little-button @click="$emit('remove', habit)">
            Click
          </my-little-button>
          <p class="habit__description">
            {{ habit.description }}
          </p>
          <div class="days__wrapper">
            <input
                type="checkbox"
                :value="day"
                v-for="day in days"
                :key="day"
            >
          </div>
        </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "HabitTracker",
  props: {
    habits: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      monthsEn: [
        'Jan', 'Feb', 'Mar',
        'Apr', 'May', 'Jun',
        'Jul', 'Aug', 'Sep',
        'Oct', 'Nov', 'Dec'
      ],
      days: [
        1, 2, 3, 4, 5, 6, 7,
        8, 9, 10, 11, 12, 13, 14,
        15, 16, 17, 18, 19, 20, 21,
        22, 23, 24, 25, 26, 27, 28,
        29, 30, 31,
      ],
      activeMonthIndex: 0,
    }
  },
  methods: {

  }
}
</script>

<style scoped lang="scss">

.tracker {
  margin-top: 20px;
}

.tracker__header {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

.tracker__inner {

}

.month__names {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 60vw;
}

.month {
  font-weight: 300;
  font-size: 1.7rem;
  line-height: 44px;
}

.month__name {
  font-weight: 300;
  font-size: 1.7rem;
  line-height: 44px;
  transition: .3s;
}

.month__name.active {
  color: red;
}

.month__name:hover {
  color: #a8a8a8;
  cursor: pointer;
  transition: .3s;
}

.habit_item {
  font-weight: 300;
  font-size: 1rem;
  line-height: 25px;
  display: flex;
  align-items: center;
  width: 100%;
  margin-top: 10px;
}

.habit__description {
  margin-left: 5px;
  max-width: 300px;
  width: 100%;
}


.days__wrapper {
  min-width: 650px;
  display: flex;
  justify-content: space-between;
  width: 100%;
}




</style>