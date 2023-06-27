<template>
    <form @submit.prevent="saveToken">
        <div v-if="campos >= 1">
            <label for="email">E-mail:</label>
            <br />
            <input type="email" id="email" />
        </div>
        <div v-if="campos >= 2">
            <label for="nome">Nome:</label>
            <br />
            <input type="text" id="nome" />
        </div>
        <div v-if="campos >= 3">
            <label for="celular">Celular:</label>
            <br />
            <input type="tel" id="celular" />
        </div>
        <div v-if="campos >= 4">
            <label for="genero">Gênero:</label>
            <br />
            <select id="genero">
                <option disabled selected>Selecione:</option>
                <option>Masculino</option>
                <option>Feminino</option>
                <option>Outro</option>
            </select>
        </div>
        <div v-if="coleta == true">
            <input type="checkbox" id="coleta" name="vehicle1" value="true">
            <label for="coleta"> Eu aceito que meus dados sejam coletados.</label><br>
        </div>
        <div>
            <input type="submit" value="Enviar" />
        </div>
    </form>
</template>

<script>
export default {
    name: "PopupForm",
    props: {
        campos: {
            type: Number,
            required: true,
        },
        coleta: {
            type: Boolean,
            required: true,
        },
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

form {
    font-family: 'Montserrat', sans-serif;
}

form > div {
    padding: 5px;
}

form input[type=email], form input[type=text], form input[type=tel] {
    width: 50%;
}
</style>