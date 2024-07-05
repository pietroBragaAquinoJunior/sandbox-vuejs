<script lang="ts">
    export default {
        data(){
            return {
                characterList: [{name:"Hinata"},{name:"Zuko"},{name:"Elizabeth"},{name:"Zack"}],
            }
        },
    }
</script>
<template>
    <ul v-for="(character, index) in characterList" :key="`character-${index}`">
        <li>{{ character.name }}</li>
    </ul>
</template>