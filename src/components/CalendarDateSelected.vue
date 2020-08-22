<template>
  <div class="calendar__header_date">{{ selectedMonth }}</div>
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