<template>
  <div id="app">
    
    <Main />
  </div>
</template>

<script>
import Main from './components/Main';

export default {
  name: 'App',
  components: {
    Main,
  }
}
</script>

<style scoped lang="scss">
    *{
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    div{
      min-height: 100vh;
      background-color: grey;
    }
</style>
