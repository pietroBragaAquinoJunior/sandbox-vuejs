<script lang="ts">
export default {
  data() {
    return {
      userData: {
        type: Object
      }
    }
  },
  methods: {
    async fetchUsers() {
      this.userData = await fetch('https://jsonplaceholder.typicode.com/users').then((response) =>
        response.json()
      )
    }
  },
  created() {
    this.fetchUsers()
  }
}
</script>

<template>
  <div>
    <h2>FETCH USERS</h2>
    <ul v-for="(user, index) in userData" :key="`user.name-${index}`">
      <li>{{ user.name }}</li>
    </ul>
  </div>
</template>
