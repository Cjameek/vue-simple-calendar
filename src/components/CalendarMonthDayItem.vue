<template>
  <td class="calendar-days__day" :class="{'calendar-days__day--not-current': !isCurrentMonth, 'calendar-days__day--today': isCurrentDay}">
      <button class="calendar-days__button" href="#">
        <span class="calendar-days__label">{{label}}</span>
      </button>
  </td>
</template>

<script>
import dayjs from "dayjs";
export default {
    name: 'CalendarMonthDayItem',
    props: {
        day: {
            type: Object,
            required: true
        },
        isCurrentMonth: {
            type: Boolean,
            required: true
        },
        isCurrentDay: {
            type: Boolean,
            required: true
        }
    },
    computed: {
        label() {
            return dayjs(this.day.date).format("D");
        }
    }
}
</script>