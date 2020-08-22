<template>
  <div class="calendar__legend calendar-legend">
      <div class="calendar-legend__item">
          <span class="calendar-legend__text">Current Day</span>
          <span class="calendar-legend__icon" aria-hidden="true"></span>
      </div>
  </div>
</template>

<script>
export default {
    name: "CalendarLegend",
    props: {
        legends: Object
    }
}
</script>