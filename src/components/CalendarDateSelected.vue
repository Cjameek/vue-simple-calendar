<template>
  <div class="calendar-current-date">{{ selectedMonth }}</div>
</template>

<script>
export default {
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