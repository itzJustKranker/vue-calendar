<template>
  <div>
    <section class="month">
      <header>
        <h1>{{ new Date().toLocaleString('en-us', { month: 'long'}) }} {{ new Date().getFullYear() }}</h1>
        <nav role='padigation'>
          <span></span>
          <span></span>
        </nav>
      </header>

      <article>
        <div class="days">
          <b>SU</b>
          <b>MO</b>
          <b>TU</b>
          <b>WE</b>
          <b>TH</b>
          <b>FR</b>
          <b>SA</b>
        </div>
        <div class="dates">
          <CalendarWeek v-for="(week, index) in calendar" :key="'week' + index" :week="week" />
        </div>
      </article>
    </section>
  </div>
</template>

<script>
import moment from 'moment'
import CalendarWeek from './CalendarWeek'

export default {
  name: 'Calendar',
  components: {
    CalendarWeek
  },
  created () {
    this.init();
  },
  data () {
    return {
      startWeek: moment().startOf('month').week(),
      endWeek: moment().endOf('month').week(),
      calendar: [],
    }   
  },
  methods: {
    init() {
      for(var week = this.startWeek; week < this.endWeek + 1; week++){
        this.calendar.push({
          week:week,
          days:Array(7).fill(0).map((n, i) => moment().week(week).startOf('week').clone().add(n + i, 'day'))
        });
      }
    }
  }
}
</script>
