<script setup>
const props = defineProps(['valorPrimeiroInput', 'valorSegundoInput', 'filtro', 'selecionaFiltro'])
</script>

<template>
    <form>
        <div class="row justify-content-center align-items-center mt-4">
            <div class="col-md-5 mt-2">
                <p class="h6">
                    Escolha a operação:
                </p>
            </div>
            <div class="col-md-6">
                <select @change="props.selecionaFiltro" class="form-control w-100 text-center">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
        <div class="row mt-3 justify-content-center">
            <div class="col-md-4 p-0">
                <input @keyup="props.valorPrimeiroInput" type="number" class="form-control" placeholder="Primeiro valor">
            </div>
            <div class="col-md-1 p-0 text-center">
                <p class="fs-4 m-0" v-if="props.filtro === 'soma'">+</p>
                <p class="fs-4 m-0" v-else-if="props.filtro === 'subtracao'">-</p>
                <p class="fs-4 m-0" v-else-if="props.filtro === 'multiplicacao'">*</p>
                <p class="fs-4 m-0" v-else>/</p>
            </div>
            <div class="col-md-4 p-0">
                <input @keyup="props.valorSegundoInput" type="number" class="form-control mb-3" placeholder="Segundo valor">
            </div>
        </div>
    </form>
</template>