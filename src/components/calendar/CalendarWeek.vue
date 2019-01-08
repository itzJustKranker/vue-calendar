<template>
  <div>
    <CalendarCell v-for="(day, index) in days" :key="'cell' + index" :day="day" :disable="isDisabled(day)"/>
  </div>
</template>

<script>
import moment from 'moment';
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
    },
    methods: {
      isDisabled (day) {
        return (moment().month() !== day.month())
      }
    }
}
</script>