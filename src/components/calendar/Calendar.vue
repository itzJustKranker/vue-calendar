<template>
  <div>
    <section class="mounth" id="january">
      <header>
        <h1>JANUARY 2013</h1>
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
          <span class="disable">30</span>
          <span class="disable">31</span>
          
          <CalendarCell v-for="(date, index) in 31" :key="index" :cell-date="date"/>
          
          <span class="disable">1</span>
          <span class="disable">2</span>
          <span class="disable">3</span>
          <span class="disable">4</span>
          <span class="disable">5</span>
          <span class="disable">6</span>
          <span class="disable">7</span>
          <span class="disable">8</span>
          <span class="disable">9</span>
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
  }
}
</script>
