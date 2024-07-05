<script>
    export default {
        emits: ['change-name']
    }
</script>

<template>
    <div>
        <button @click="$emit('change-name')">Change Name</button>
    </div>
    <hr>
</template>