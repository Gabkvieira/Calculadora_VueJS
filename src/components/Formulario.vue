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
            <div class="col-md-4 alteraCelular">
                <select @change="props.trocarFiltro" class="alinhaTexto form-control border-dark">
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
    text-align: center;
}

.alinhaTexto {
    text-align: center;
}

@media only screen and (max-width: 767px) {
    .alteraCelular {
        margin-top: 16px;
    }

    form input {
    margin-right: 3px;
}
}
</style>