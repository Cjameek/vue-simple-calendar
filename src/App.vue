<template>
  <div id="app">
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
