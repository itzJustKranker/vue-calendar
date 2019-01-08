<template>
<div class="cell-wrapper" :class="{ disable }">
  <div class="cell">
      <span class="cell-date">{{ day.format('DD') }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalendarCell',
  props: ['disable', 'day']
}
</script>
