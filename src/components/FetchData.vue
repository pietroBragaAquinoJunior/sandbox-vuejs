<script lang="ts">
export default {
  data() {
    return {
      pokedex: ''
    }
  },
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon/ditto').then((response) =>
        response.json()
      )
    }
  }
}
</script>

<template>
  <div>
    <h2>Fetch data</h2>
    <pre>{{ pokedex }}</pre>
    <button @click="fetchPokemon">Pokemon</button>
  </div>
</template>
