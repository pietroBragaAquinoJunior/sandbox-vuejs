<script lang="ts">
    export default {

    }
</script>

<template>
    <div>
        <main class="main">
            <slot name="main"></slot>
        </main>
        <footer class="footer">
            <slot name="footer"></slot>
        </footer>
    </div>
</template>

<style>
    .main{
        background: green;
    }
    .footer{
        background: purple;
    }
</style>