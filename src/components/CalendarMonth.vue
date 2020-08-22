<template>
  <section class="calendar__month">
    <div class="calendar__header">
      <CalendarDateSelected 
        :selected-date="selectedDate"
      />
      <CalendarDatePagination 
        :current-date="today"
        :selected-date="selectedDate"
        @dateSelected="selectDate"
      />
    </div>

    <CalendarWeekdays/>

    <ol class="calendar__days-list calendar-days">
      <!-- <CalendarMonthDayItem/> -->
    </ol>
  </section>
</template>

<script>
import dayjs from "dayjs";
import weekday from "dayjs/plugin/weekday";
import weekOfYear from "dayjs/plugin/weekOfYear";

import CalendarDateSelected from './CalendarDateSelected';
import CalendarDatePagination from './CalendarDatePagination';
import CalendarWeekdays from './CalendarWeekdays';

dayjs.extend(weekday);
dayjs.extend(weekOfYear);

export default {
  name: 'CalendarMonth',
  components: {
    CalendarDateSelected,
    CalendarDatePagination,
    CalendarWeekdays
  },
  data() {
    return {
      selectedDate: dayjs(),
      today: dayjs().format("YYYY-MM-DD")
    };
  },
  methods: {
    selectDate(newDateSelection) {
      this.selectedDate = newDateSelection;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
