<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <Cronometro :tempoEmSegundos="tempoEmSegundos" />
        <BotaoTemporizador icone="fas fa-play" :desabilitado="cronometroRodando"  textoBotao="play" @clicado="iniciar"/>
        <BotaoTemporizador icone="fas fa-stop" :desabilitado="!cronometroRodando"  textoBotao="stop" @clicado="finalizar"/>
    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import BotaoTemporizador from './BotaoTemporizador.vue';
export default defineComponent({
    name: "TemporizadorTarefa",
    emits: ['aoTemporizadorFinalizado'],
    components: {
        Cronometro,
        BotaoTemporizador
    },
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    methods: {
        iniciar() {
            this.cronometroRodando = true;
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos++
            }, 1000);
        },
        finalizar() {
            this.cronometroRodando = false;
            clearInterval(this.cronometro);
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
            this.tempoEmSegundos = 0
        }
    }
})
</script>