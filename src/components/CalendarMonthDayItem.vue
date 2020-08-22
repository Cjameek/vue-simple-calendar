<template>
  <li class="calendar-days__day" :class="{'calendar-days__day--not-current': !isCurrentMonth, 'calendar-days__day--today': isCurrentDay}">
      <span class="calendar-days__label">{{label}}</span>
  </li>
</template>

<script>
import dayjs from "dayjs";
export default {
    name: 'CalendarMonthDayItem',
    props: {
        day: {
            type: Object,
            required: true
        },
        isCurrentMonth: {
            type: Boolean,
            required: true
        },
        isCurrentDay: {
            type: Boolean,
            required: true
        }
    },
    computed: {
        label() {
            return dayjs(this.day.date).format("D");
        }
    }
}
</script>

<style lang="scss" scoped>
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
</style>