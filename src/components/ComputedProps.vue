<script lang="ts">
    export default {
        props:{
            usuario:{
                type: Object,
                required: true
            }
        }
    }
</script>

<template>
    <div>{{ usuario.nome }}</div>
    <div>{{ usuario.profissao }}</div>
    <hr/>
</template>