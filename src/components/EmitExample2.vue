<script lang="ts">
    export default {
        emit: ["teste"]
    }
</script>

<template>
    <div>
        <button @click="$emit('teste')">clique-me e olhe o console</button>
    </div>
    <hr/>
</template>