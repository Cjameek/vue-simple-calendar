<template>
  <div id="calendar" class="calendar">
    <h2>Example Calendar</h2>
    <CalendarMonth/>
  </div>
</template>

<script>
/**
 * App idea based off the following tutorial - https://css-tricks.com/lets-make-a-vue-powered-monthly-calendar/
 */
import CalendarMonth from './components/CalendarMonth.vue'

export default {
  name: 'App',
  components: {
    CalendarMonth
  }
}
</script>

<style>
#calendar {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 500px;
  margin: auto;
  padding: 50px 0;
}
* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
ul,
ol {
  margin: 0;
  padding-left: 0;
}
</style>
