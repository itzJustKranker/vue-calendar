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
          <CalendarCell v-for="(date, index) in prevMonthDatesDisabled" :key="'prevMonthDisabled' + index" :cell-date="date" :disable="true"/>
          
          <CalendarCell v-for="(date, index) in currentMonthDates" :key="'currentMonth' + index" :cell-date="date"/>
          
          <CalendarCell v-for="(date, index) in nextMonthDatesDisabled" :key="'nextMonthDisabled' + index" :cell-date="date" :disable="true"/>
        </div>
      </article>
    </section>
  </div>
</template>

<script>
import CalendarCell from './CalendarCell';

export default {
  name: 'Calendar',
  components: {
    CalendarCell
  },
  data () {
    return {
      prevMonthDatesDisabled: new Array(2).fill(0).map((e,i)=>i+1),
      currentMonthDates: new Array(31).fill(0).map((e,i)=>i+1),
      nextMonthDatesDisabled: new Array(9).fill(0).map((e,i)=>i+1)
    }   
  }
}
</script>
