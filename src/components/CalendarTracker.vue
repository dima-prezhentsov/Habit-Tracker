<template>
<div class="container">
    <div class="header_info"><p class="month">January</p> <p class="year">2022</p></div>
    <div class="item" v-for="day in days" :key="day">
    {{ day }}
  </div>
</div>
</template>

<script>
export default {
  name: "CalendarTracker",
  data() {
    return {
      days: [
          1, 2, 3, 4, 5, 6, 7,
          8, 9, 10, 11, 12, 13, 14,
          15, 16, 17, 18, 19, 20, 21,
          22, 23, 24, 25, 26, 27, 28,
          29, 30, 31,
      ]
    }
  }
}
</script>

<style scoped lang="scss">

p {
  margin: 0;
}

.container {
  width: 700px;
  height: 630px;
  display: grid;
  grid-template: repeat(5, 64px) / repeat(7, 64px);
  grid-gap: 10px;
  justify-content: center;
  align-content: center;
}

.header_info {
  grid-column: 1 / 8;
  display: flex;
  align-items: center;
  justify-content: space-between;

  .year {
    font-weight: 400;
    font-size: 36px;
    line-height: 49px;
  }

  .month {
    font-weight: 600;
    font-size: 36px;
    line-height: 49px;
  }
}

.item {
  font-weight: 600;
  font-size: 32px;
  line-height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 64px;
  height: 64px;
}

</style>