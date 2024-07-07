<script setup>
    import { ref, computed, reactive } from 'vue'

    const usersList = await fetch('https://jsonplaceholder.typicode.com/users').then(res => res.json())
    
    const regionName = ref("Teste")
    
    const regionNameAllCaps = computed(() => {
        return regionName.value.toUpperCase();
    })

    const state = reactive({
        primeiro: "uhul",
        segundo: "uhul2"
    })

    const upperOnStates = () => {
        state.primeiro = state.primeiro.toUpperCase()
        state.segundo = state.segundo.toUpperCase()
    }

    const changeRegionName = () =>{
        regionName.value = "pietro"
    }

    const regionNameToLowerCase = computed(()=>{
        return regionName.value.toLowerCase();
    })
    
</script>

<template>
    <div>
        <h2>{{ regionName }}</h2>
        <h3>{{ regionNameAllCaps }}</h3>
        <h3>{{ regionNameToLowerCase }}</h3>
        <button @click="changeRegionName">Change region name</button>
        <h4>{{ state.primeiro }} - {{ state.segundo }}</h4>
        <button @click="upperOnStates">Upper on state</button>
        <pre>{{ usersList }}</pre>
    </div>
</template>