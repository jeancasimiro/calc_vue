<script setup>
import { reactive } from 'vue'


const estado = reactive({
  sel: 'adicao',
  num1: '',
  num2: '',
  resultado: '',
})

</script>

<template>
  <div class="container mt-5 text-center">
    <h1 class="h3 mb-3">Selecione a operação que deseja fazer:</h1>
    <div class="row text-center justify-content-center">
      <select v-model="estado.sel" class="form-select">
        <option value="adicao" selected>Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>
    <div class="row text-center justify-content-center mt-4">
      <input class="col-md-4 form-control" type="number" name="num1" id="" placeholder="1° número">
    </div>
    <p class="h3" v-if="estado.sel === 'adicao'">+</p>
    <p class="h3" v-if="estado.sel === 'subtracao'">-</p>
    <p class="h3" v-if="estado.sel === 'multiplicacao'">x</p>
    <p class="h3" v-if="estado.sel === 'divisao'">/</p>
    <div class="row text-center justify-content-center mt-1">
      <input class="col-md-4 form-control" type="number" name="num2" id="" placeholder="2° número">
    </div>
    <p class="h3">=</p>
    <div class="row text-center justify-content-center mt-1">
      <input readonly v-model="resultado" class="col-md-4 form-control" type="number" name="resultado" placeholder="Resultado">
    </div>
  </div>
</template>

<style scoped>
.form-select,
.form-control {
  max-width: 200px;
}
</style>
