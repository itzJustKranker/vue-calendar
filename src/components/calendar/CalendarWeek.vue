<template>
  <div>
    <CalendarCell v-for="(day, index) in days" :key="'cell' + index" :day="day"/>
  </div>
</template>

<script>
import CalendarCell from './CalendarCell'

export default {
    name: 'CalendarWeek',
    props: ['week'],
    components: {
      CalendarCell
    },
    data () {
      return {
        days: this.week.days
      }
    }
}
</script>