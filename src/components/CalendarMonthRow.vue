<template>
  <tr class="calendar__row">
    <CalendarMonthDayItem
        v-for="day in getAllDays"
        :key="day.date"
        :day="day"
        :is-current-month="day.isCurrentMonth"
        :is-current-day="day.date === getCurrentDay"
      />
  </tr>
</template>

<script>
import CalendarMonthDayItem from './CalendarMonthDayItem';
export default {
    name: 'CalendarMonthRow',
    components: {
        CalendarMonthDayItem
    },
    props: {
        row: {
            type: Array,
            required: true
        },
        today: {
            type: String,
            required: true
        }
    },
    computed: {
        getAllDays() {
            return this.row;
        },
        getCurrentDay() {
            return this.today;
        }
    }
}
</script>