<template>
  <tr class="calendar__row calendar__weekdays">
      <th class="calendar__weekday" v-for="weekday in weekdays" :key="weekday">
          {{weekday}}
      </th>
  </tr>
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