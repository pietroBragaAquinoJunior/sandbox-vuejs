<script lang="ts">
    export default {
        data(){
            return{
                força: 10,
                vitalidade:10
            }
        },
        computed:{
            hpTotal(){
                return this.força * this.vitalidade
            }
        },
        methods:{
            mudarHpMudandoForcaEVitalidade(){
                this.força = this.força + 2
                this.vitalidade = this.vitalidade + 1
            }
        }
    }
</script>
<template>
    <button @click="mudarHpMudandoForcaEVitalidade">Mudar hp total mudando força e vitalidade</button>
    <div>
        {{ hpTotal }}
    </div>
    <hr>
</template>