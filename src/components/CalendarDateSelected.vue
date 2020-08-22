<template>
  <h3 class="calendar__header_date">{{ selectedMonth }}</h3>
</template>

<script>
export default {
    name: 'CalendarDateSelected',
    props: {
        selectedDate: {
            type: Object,
            required: true
        }
    },
    computed: {
        selectedMonth() {
            return this.selectedDate.format("MMMM YYYY");
        }
    }
}
</script>

<style>

</style>