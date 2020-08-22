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

<style>

</style>