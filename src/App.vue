<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
import './assets/scss/_app.scss';
import Home from './views/Home';

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>
