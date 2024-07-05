<script lang="ts">
    export default {
        props: {
            mensagem: {
                type: String,
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
        <p>
        {{ mensagem }}
    </p>
    <hr/>
</div>

</template>