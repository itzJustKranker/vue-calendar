<template>
  <div class="cell" :class="{ disable }">
    <span class="cell-date">{{ cellDate }}</span>
  </div>
</template>

<script>
export default {
  name: 'CalendarCell',
  props: ['disable', 'cellDate']
}
</script>
