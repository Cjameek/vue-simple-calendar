<template>
  <nav class="calendar__header_pagination calendar-pagination">
      <ul class="calendar-pagination__list">
          <li class="calendar-pagination__list-item">
              <button @click="selectPrevious" class="calendar-pagination__button calendar-pagination__button--previous">Previous</button>
          </li>
          <li class="calendar-pagination__list-item">
            <button @click="selectCurrent" class="calendar-pagination__button calendar-pagination__button--current">Current</button>
          </li>
          <li class="calendar-pagination__list-item">
            <button @click="selectNext" class="calendar-pagination__button calendar-pagination__button--next">Next</button>
          </li>
      </ul>
  </nav>
</template>

<script>
import dayjs from "dayjs";

export default {
    name: 'CalendarDatePagination',
    props: {
        currentDate: {
            type: String,
            required: true
        },
        selectedDate: {
            type: Object,
            required: true
        }
    },
    methods: {
        selectPrevious() {
            let dateSelection = dayjs(this.selectedDate).subtract(1, "month");
            this.$emit("dateSelected", dateSelection);

        },
        selectCurrent() {
            let dateSelection = dayjs(this.currentDate);
            this.$emit("dateSelected", dateSelection);
        },
        selectNext() {
            let dateSelection = dayjs(this.selectedDate).add(1, "month");
            this.$emit("dateSelected", dateSelection);
        }
    }
}
</script>