<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
      <div class="d-flex">
        <div class="col-8"><ComponenteCalculadora></ComponenteCalculadora></div>
        <div class="4"><ComponenteTitulo></ComponenteTitulo></div>
      </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import ComponenteTitulo from './components/ComponenteTitulo.vue';
import ComponenteCalculadora from './components/ComponenteCalculadora.vue';

@Component({
  components: {
    HelloWorld,
    ComponenteTitulo,
    ComponenteCalculadora,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  background: grey;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
