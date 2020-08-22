<template>
  <a class="calendar__skip" :href="link">Skip Calendar Dates</a>
</template>

<script>
export default {
    name: "CalendarSkip",
    props: {
        link: String
    }
}
</script>