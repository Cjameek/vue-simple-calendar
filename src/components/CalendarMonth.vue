<template>
  <section class="calendar-month">
    <div class="calendar-header">
      <CalendarDateSelected />
      <!-- <CalendarDatePagination /> -->
    </div>

    <!-- <CalendarWeekdays/> -->

    <ol>
      <!-- <CalendarGrid/> -->
    </ol>
  </section>
</template>

<script>
import CalendarDateSelected from './CalendarDateSelected.vue'

export default {
  props: {
    //msg: String
  },
  components: {
    CalendarDateSelected
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
