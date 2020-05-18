<template>
  <div class="row">
    <div class="col-6">
      <div class="row">
        <div class="col-4" v-for="(numero, index) in numeros" :key="index">
          <button @click="presionarBoton(numero)" class="btn btn-danger w-100 m-2">
            {{numero}}</button>
        </div>
      </div>
      <div class="row col-12 mx-auto">
        <div class="col-6">
          <button @click="sumarHistorial" class="btn btn-primary">Calcular Resultado</button>
        </div>
        <div class="col-6">
          <button @click="limpiarHistorial" class="btn btn-primary">Limpiar Historial</button>
        </div>
      </div>
    </div>
    <div class="col-6">

      <h2 :style="estilo1">HOLA</h2>
      <h2>Historial {{suma}} {{nombreUsusario}}</h2>


      <form @submit="enviarFormulario">
        <input type="text" placeholder="Nombre" v-model="nombreUsusario">
        <textarea v-model="descripcionUsuario"></textarea>
           <select v-model="opcion">
          <option value="">Seleccione una opcion</option>
          <option value="1">Valor 1</option>
          <option value="2">Valor 2</option>
       </select>
       <input type="checkbox" v-model="aceptaTerminos">
        <button type="submit"> Enviar Formulario </button>
      </form>

      <table>
        <tr v-for="(historial, index) in historial" :key="index">
          <td>{{historial}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script lang="ts">
// Computed properties, typescript properties
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class ComponenteCalculadora extends Vue {
  numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9];

  historial: number[] = [];

  suma = 0;

  nombre = 'Juan Diego';

  apellido = 'Giraldo';

  bandera = false;

  nombreUsusario = '';

  descripcionUsuario = '';

  opcion ='';

  aceptaTerminos=false;

  get nombreCompleto() {
    // Templeate Literal +
    return ` EL nombre completo es: ${this.nombre} ${this.apellido}`;
  }

  get estilo1() {
    return this.bandera ? 'color:red;' : 'color:blue;';
  }

  presionarBoton(valor: number) {
    this.bandera = true;
    this.historial.push(valor);
  }

  sumarHistorial() {
    this.historial.forEach((historial) => {
      this.suma += historial;
    });
  }

  enviarFormulario(event: any) {
    if (this.aceptaTerminos === false) {
      alert('Debes aceptar los terminos');
    } else {
      alert('gracias');
    }
  }

  limpiarHistorial() {
    this.bandera = false;
    this.historial = [];
    this.suma = 0;
  }
}
</script>
<style>
</style>
