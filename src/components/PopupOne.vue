<template>
    <div class="popup popupOne">
        <span class="close close-1" @click="closeModal">&times;</span>
        <h1>{{ titulo }}</h1>
        <h2>{{ subtitulo }}</h2>
        <div class="video">
            <iframe :src="url"></iframe>
        </div>
        <PopupForm :campos="campos" :coleta="coleta" />
    </div>
</template>

<script>
import config from '../../config.json';
import PopupForm from './PopupForm.vue';

export default {
    name: "popupOne",
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
            this.$emit('closemodalone');
        }
    }
}
</script>

<style scoped>
iframe {
  width: 100%;
  height: 300px;
}
</style>
