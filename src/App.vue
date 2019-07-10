<template>
  <div id="app">
    <Navigation homelink="http://github.com/valdise"/>
    <ControlPanel></ControlPanel>

  </div>
</template>

<script>
import Navigation from './components/Navigation.vue'
import ControlPanel from './components/ControlPanel.vue'

export default {
  name: 'app',
  components: {
    Navigation,
    ControlPanel
  }
}
</script>

<style>
*{margin: 0; padding: 0}
#app {}
</style>
