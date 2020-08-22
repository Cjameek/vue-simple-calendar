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

<style lang="scss">
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
.calendar {
    &__month {
      border-radius: 30px;
      padding: 30px;
      box-shadow: 0px 0px 15px -5px rgba(0,0,0,.5);
    }
    &__days-list {
        background-color: #fdfdfd;
        display: flex;
        flex-wrap: wrap;
        border-bottom-left-radius: 10px;
        border-bottom-right-radius: 10px;
    }
    &__weekdays {
        background-color: #f6f6f6;
        display: flex;
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
    }

    &__weekday {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 14.28571%;
        height: 50px;
        font-size: 14px;
        font-weight: 700;
        text-align: center;
    }
}
.calendar-pagination {
    &__list {
        list-style-type: none;
        display: flex;
        justify-content: space-between;
        padding: 24px 0;
    }
    &__button {
        background-color: #ccc;
        border-radius: 5px;
        border: none;
        padding: 12px 25px;
        font-weight: 700;
        cursor: pointer;
        transition: background-color 300ms ease;

        &:hover,
        &:focus {
            background-color: darken(#ccc, 10%);
        }
    }
}
.calendar-days {
    &__day {
        background-color: transparent;
        position: relative;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 14.28571%;
        height: 50px;
        font-size: 14px;
        text-align: center;
        cursor: pointer;
        transition: background-color 300ms ease, opacity 300ms ease;

        &:hover,
        &:focus {
            background-color: #f0f0f0;
            opacity: 1;
        }

        &--not-current {
            opacity: .5;
        }

        &--today {
            .calendar-days {
                &__label {
                    background-color: blue;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    border-radius: 30px;
                    padding: 5px;
                    width: 30px;
                    height: 30px;
                    color: #fff;
                    font-weight: 700;
                }
            }
        }
    }
}
* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
ul,
ol {
  margin: 0;
  list-style-type: none;
  padding: 0;
}
h3 {
  margin: 0;
}
a {
  color: #42b983;
}
</style>
