<script setup>
const props = defineProps(["numero1", "numero2", "trocarFiltro"]);
</script>

<template>
    <form>
        <div class="row">
            <div class="col d-flex">
            <input @keyup="props.numero1" required type="number" placeholder="Digite o primeiro número" class="form-control border-dark">
            <input @keyup="props.numero2" required type="number" placeholder="Digite o segundo número" class="form-control border-dark">
            </div>
            <div class="col-md-4">
                <select @change="props.trocarFiltro" class="form-control border-dark">
                    <option value="adicao">Adição</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>]
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
form input {
    margin-right: 16px;
}
</style>