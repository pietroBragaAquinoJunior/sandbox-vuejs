<script>
    export default {
        emit: ["adicionar-personagem-lista"],
        data(){
            return {
                lista: [{name:"pietro"},{name:"cesar"},{name:"paulo"}]
            }
        }
    }
</script>

<template>
    <div>
        <ul v-for="(personagem,index) in lista" :key="`personagem.name-${index}`">
            <li>{{ personagem.name }}</li>
            <button @click="$emit('adicionar-personagem-lista', personagem)">adicionar na lista</button>
        </ul>
    </div>
    <hr/>
</template>