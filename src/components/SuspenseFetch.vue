<script lang="ts">
export default {
  async setup() {
    const users = await fetch('https://jsonplaceholder.typicode.com/users').then((res) =>
      res.json()
    )
    return {
      users
    }
  }
}
</script>
<template>
  <div>
    <pre>{{ users }}</pre>
  </div>
</template>
