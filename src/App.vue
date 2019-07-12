<template>
  <div id="app">
    <v-app>
      <Navigation homelink="http://github.com/valdise" />
      <v-container fluid>
        <v-layout row wrap>
          <v-flex md3>
            <ControlPanel></ControlPanel>
          </v-flex>
          <v-flex md9>
            <DisplayPanel width="displayWidth" height="displayHeight"></DisplayPanel>
          </v-flex>
        </v-layout>
        
      </v-container>
    </v-app>
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import ControlPanel from "./components/ControlPanel.vue";
import DisplayPanel from "./components/DisplayPanel.vue";

export default {
  name: "app",
  data() {
    return {
      displayWidth: null,
      displayHeight: null
    }
  },
  components: {
    Navigation,
    ControlPanel,
    DisplayPanel
  },
  mounted() {
    this.displayWidth = 600;
    this.displayHeight = 600
  }
};
</script>

<style>
</style>
