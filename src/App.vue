<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Main from './components/Main';
import Header from './components/Header';

export default {
  name: 'App',
  components: {
    Main,
    Header
  }
}
</script>

<style lang="scss">

</style>
