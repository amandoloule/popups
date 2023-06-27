<template>
    <div class="popup popupTwo">
        <span class="close" @click="closeModal">&times;</span>
        <h1>{{ titulo }}</h1>
        <h2>{{ subtitulo }}</h2>
        <div class="game">
            <img src="../../public/game.png" alt="Game">
        </div>
        <PopupForm :campos="campos" :coleta="coleta" />
    </div>
</template>

<script>
import config from '../../config.json';
import PopupForm from './PopupForm.vue';

export default {
    name: "popupTwo",
    components: {
        PopupForm,
    },
    data() {
        return {
            campos: config.campos,
            coleta: config.coleta,
            url: config.url,
            titulo: config.titulo,
            subtitulo: config.subtitulo
        };
    },
    methods: {
        closeModal() {
            this.$emit('closemodaltwo');
        }
    }
}
</script>

<style scoped>
.game img {
  width: 100%;
}
</style>
