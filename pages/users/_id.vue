<template>
  <div>
    <div v-if="user">User name: {{ user.name }}</div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    console.log('user ID >>', params.id)
    const user = await $axios.$get(`https://jsonplaceholder.typicode.com/users/${params.id}`)
    return { user }
  },
}
</script>
