<template>
    <div class="box has-text-weight-bold" :style="estilo">
        <slot></slot>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'boxTarefa',
    data(){
        return {
            estilo: {
                background:'#FAF0CA'
            },
        }
    }

})
</script> 

<style scoped>

</style>