<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="">
        </h1>
        <button class="button is-large" @click="alterarTema()">
            <span class="icon">
                <i class="fas fa-lg" :class="iconeBotao"></i>
            </span>
        </button>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BarraLateral',
    emits:['aoTemaAlterado'],
    data(){
        return{
            modoEscuroAtivo: false
        }
    },
    computed: {
        iconeBotao() {
            if (this.modoEscuroAtivo) {
                return 'fa-sun'
            }
            return 'fa-moon'
        }
    },
    methods:{
        alterarTema(){
            this.modoEscuroAtivo = !this.modoEscuroAtivo
            this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
        }
    }
})
</script> 

<style scoped>
    header {
        padding: 1rem;
        background: #0d3b66;
        width: 100%;
        height: 100vh;
        text-align: center;
    }
    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }
</style>