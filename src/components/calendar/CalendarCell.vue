<template>
<div 
  class="cell-wrapper" 
  :class="{
    'active': isSelected,
    disable 
  }"
  >
  <div class="cell">
    <span class="cell-date">
      {{ day.format('DD') }}
    </span>
  </div>
</div>
</template>

<script>
export default {
  name: 'CalendarCell',
  props: ['day', 'isSelected', 'disable' ]
}
</script>
