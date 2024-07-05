<script>
export default {
    props:{
        incrementarContadorDoComponentePai:{
            type: Function,
            required: true
        }
    },
    data(){
        return {
        
        }
    }
}
</script>

<template>
    <div>
        <button @click="incrementarContadorDoComponentePai">Incrementar Contador do Componente Pai</button>
        <hr/>
   </div>
</template>