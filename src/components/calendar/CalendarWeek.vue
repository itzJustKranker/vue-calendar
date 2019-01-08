<template>
  <div>
    <CalendarCell 
      v-for="(day, index) in days" 
      :key="'cell' + index" 
      :day="day"
      :isSelected="selected[index]"
      :disable="isDisabled(day)"
      v-on:click="setSelected(index)"
      />
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
        days: this.week.days,
        selected: new Array(this.week.days.length).fill(false)
      }
    },
    methods: {
      isDisabled (day) {
        return (moment().month() !== day.month())
      },
      setSelected (i) {
        this.selected[i] = true
      }
    }
}
</script>