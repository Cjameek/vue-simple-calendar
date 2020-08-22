<template>
  <ol class="calendar__weekdays">
      <li class="calendar__weekday" v-for="weekday in weekdays" :key="weekday">
          {{weekday}}
      </li>
  </ol>
</template>

<script>
const WEEKDAYS = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];

export default {
    name: 'CalendarWeekdays',
    computed: {
        weekdays() {
            return WEEKDAYS;
        }
    }
}
</script>

<style lang="scss" scoped>
.calendar {
    &__weekdays {
        background-color: #f6f6f6;
        display: flex;
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
    }

    &__weekday {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 14.28571%;
        height: 50px;
        font-size: 14px;
        font-weight: 700;
        text-align: center;
    }
}
</style>