<template>
  <aside id="calendar" class="calendar">
    <h2 class="calendar__title">Example Calendar</h2>
    <CalendarMonth/>
  </aside>
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
:root {
  --calendar-bg: #fff;
  --calendar-text: #2e2e2e;
  --calendar-body: #fdfdfd;
  --calendar-heading: #f6f6f6;
  --calendar-day: #ccc;
  --calendar-button: #fff89d;
  --calendar-button-hover: #fff238;
  --current-day: blue;
}
* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
ul,
ol {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
h3 {
  margin: 0;
}

.calendar {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: var(--calendar-bg);
  text-align: center;
  color: var(--calendar-text);
  max-width: 500px;
  margin: auto;
  padding: 50px 0;
  
  &__month {
    border-radius: 30px;
    padding: 30px;
    box-shadow: 0px 0px 15px -5px rgba(0,0,0,.5);
  }
  &__days-list {
      background-color: var(--calendar-body);
      display: flex;
      flex-wrap: wrap;
      border-bottom-left-radius: 10px;
      border-bottom-right-radius: 10px;
  }
  &__row {
    display: flex;
    width: 100%;
    height: auto;
  }
  &__weekdays {
      background-color: var(--calendar-heading);
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
  &__skip {
    position: absolute;
    width: 1px;
    height: 1px;
    opacity: 0;
    pointer-events: none;
    overflow: hidden;

    &:focus {
      position: relative;
      width: 100%;
      height: auto;
      opacity: 1;
      pointer-events: visible;
    }
  }
  
  /* Pagination */
  &-pagination {
    &__list {
        list-style-type: none;
        display: flex;
        //justify-content: space-between;
        padding: 24px 0;

        &-item:nth-child(2){
          margin-left: auto;
          margin-right: 10px;
        }
    }
    &__button {
        background-color: var(--calendar-button);
        border-radius: 5px;
        border: none;
        padding: 12px 25px;
        color: var(--calendar-text);
        font-weight: 700;
        cursor: pointer;
        transition: background-color 300ms ease;

        &:hover,
        &:focus {
            background-color: var(--calendar-button-hover);
        }
    }
  }

  /* Single Days */
  &-days {
    &__day {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 14.28571%;
        height: 50px;

        &--not-current {
            opacity: .5;
        }

        &--today {
            .calendar-days {
                &__label {
                    background-color: var(--current-day);
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

    &__button {
        background-color: transparent;
        position: relative;
        width: 100%;
        height: 100%;
        border: none;
        color: var(--calendar-text);
        font-size: 14px;
        text-align: center;
        cursor: pointer;
        transition: background-color 300ms ease, opacity 300ms ease;

        &:hover,
        &:focus {
            background-color: #f0f0f0;
        }
    }

    &__label {
      margin: auto;
    }
  }

  /* Legend */
  &-legend {
    display: flex;
    justify-content: center;
    margin-top: 24px;

    &__text {
      font-size: 14px;
    }
    &__icon {
      display: inline-block;
      vertical-align: bottom;
      width: 20px;
      height: 20px;
      border-radius: 100%;
      margin-left: 10px;

      background-color: var(--current-day);
    }
  }
}
</style>
