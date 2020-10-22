<template>
  <div id="app">
    <h3>Simple tool to test v-bind:is</h3>
    <component :is="isComponent"></component>
    <button @click="toggleComp">Toggle !</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import ByeWorld from './components/ByeWorld.vue';

@Component({
  components: {
    HelloWorld,
    ByeWorld,
  },
})
export default class App extends Vue {
  toggle: boolean = true;

  get isComponent() {
    if (this.toggle) return HelloWorld;
    return ByeWorld;
  }

  toggleComp() {
    return this.toggle = !this.toggle;
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
