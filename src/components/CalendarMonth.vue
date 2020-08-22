<template>
  <section class="calendar__month">
    <div class="calendar__header">
      <!-- <CalendarDateSelected /> -->
      <!-- <CalendarDatePagination /> -->
    </div>

    <!-- <CalendarWeekdays/> -->

    <ol>
      <!-- <CalendarGrid/> -->
    </ol>
  </section>
</template>

<script>
import dayjs from "dayjs";
import weekday from "dayjs/plugin/weekday";
import weekOfYear from "dayjs/plugin/weekOfYear";

dayjs.extend(weekday);
dayjs.extend(weekOfYear);

export default {
  props: {
    //msg: String
  },
  components: {
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
