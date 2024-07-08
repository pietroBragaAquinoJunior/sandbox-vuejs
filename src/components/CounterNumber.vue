<script lang="ts">
export default {
  data() {
    return {
      count: 10
    }
  },
  methods: {
    adicionar() {
      this.count = this.count + 1
    },
    subtrair() {
      this.count = this.count + 1
    }
  }
}
</script>

<template>
  <div>{{ count }}</div>
  <button @click="adicionar">+</button>
  <button @click="subtrair">-</button>
  <hr />
</template>
