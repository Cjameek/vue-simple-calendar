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
      <CalendarMonthDayItem
        v-for="day in days"
        :key="day.date"
        :day="day"
        :is-today="day.date === today"
      />
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
import CalendarMonthDayItem from './CalendarMonthDayItem';

dayjs.extend(weekday);
dayjs.extend(weekOfYear);

export default {
  name: 'CalendarMonth',
  components: {
    CalendarDateSelected,
    CalendarDatePagination,
    CalendarWeekdays,
    CalendarMonthDayItem
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
    },
    getWeekday(date) {
      return dayjs(date).weekday();
    }
  },
  computed: {
    days() {
      return [
        ...this.previousMonthDays,
        ...this.currentMonthDays,
        ...this.nextMonthDays
      ]
    },
    month() {
      return Number(this.selectedDate.format("M"));
    },
    year() {
      return Number(this.selectedDate.format("YYYY"));
    },
    numberOfDaysInMonth() {
      return dayjs(this.selectedDate).daysInMonth();
    },
    previousMonthDays() {
      const firstDayOfTheMonthWeekday = this.getWeekday(this.currentMonthDays[0].date);
      const previousMonth = dayjs(`${this.year}-${this.month}-01`).subtract(1, "month");
      const previousMonthLastMondayDayOfMonth = dayjs(this.currentMonthDays[0].date).subtract(firstDayOfTheMonthWeekday - 1, "day").date();

      // Cover first day of the month being sunday 
      (firstDayOfTheMonthWeekday === 0)
      const visibleNumberOfDaysFromPreviousMonth = firstDayOfTheMonthWeekday ? firstDayOfTheMonthWeekday - 1 : 6;
      return [...Array(visibleNumberOfDaysFromPreviousMonth).keys()].map((day) => {
        return {
          date: dayjs(`${previousMonth.year()}-${previousMonth.month() + 1}-${previousMonthLastMondayDayOfMonth + day}`).format("YYYY-MM-DD"),
          isCurrentMonth: false
        };
      });
    },
    currentMonthDays() {
      return [...Array(this.numberOfDaysInMonth).keys()].map((day) => {
        return {
          date: dayjs(`${this.year}-${this.month}-${day}`).format("YYYY-MM-DD"),
          isCurrentMonth: true
        }
      });
    },
    nextMonthDays() {
      const lastDayOfTheMonthWeekday = this.getWeekday(`${this.year}-${this.month}-${this.currentMonthDays.length}`);
      const nextMonth = dayjs(`${this.year}-${this.month}-01`).add(1, "month");
      const visibleNumberOfDaysFromNextMonth = lastDayOfTheMonthWeekday ? 7 - lastDayOfTheMonthWeekday : lastDayOfTheMonthWeekday;

      return [...Array(visibleNumberOfDaysFromNextMonth).keys()].map((day) => {
        return {
          date: dayjs(`${nextMonth.year()}-${nextMonth.month() + 1}-${day + 1}`).format("YYYY-MM-DD"),
          isCurrentMonth: false
        };
      });
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
