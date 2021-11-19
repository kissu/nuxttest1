<template>
  <div>
    <div v-if="user">User name: {{ user.name }}</div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    console.log('user ID >>', params.id)
    const user = await $axios.$get(
      `https://jsonplaceholder.typicode.com/users/${params.id}`
    )
    return { user }
  },
  methods: {
    nice() {
      readable(new Date(), function start(set) {
        const interval = setInterval(() => {
          set(new Date())
        }, 1000)

        return function stop() {
          clearInterval(interval)
        }
      })
    },
  },
}
</script>
