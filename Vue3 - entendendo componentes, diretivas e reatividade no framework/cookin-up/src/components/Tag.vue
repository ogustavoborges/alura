<template>
    <span class="tag" :class="{ativa}">
        {{ texto }}
    </span>
</template>

<script lang="ts">
export default {
    name: 'TagCard',
    props: {
        texto: {type: String, required: true},
        ativa: Boolean
    }
}
</script>

<style scoped>
.tag {
    display: inline-block;
    border-radius: 0.5rem;
    min-width: 4.25rem;
    padding: 0.5rem;
    text-align: center;
    transition: 0.2s;
    color: var(--cinza);
    background-color: var(--cinza-claro);
    font-weight: 400;
}

.tag.ativa{
    color: var(--creme, #FFFAF3);
    background: var(--coral, #F0633C);
    font-weight: 700;
}
</style>
