<template>
  <div>
    <h1>test</h1>
    test payload : 

    <p>Path: {{ $route.path }}</p>

    data : {{ company }}
<!-- <alert>Info alert!</alert>
    <pre>
      <code v-highlight="code" class="javascript">
  export default {
    modules: [,
      '@nuxt/content'
    ],
    generate: {
      async ready () {
        const { $content } = require('@nuxt/content')
        const files = await $content().only(['slug']).fetch()
        console.log(files)
      }
    }
  }
      </code>
      </pre> -->
  </div>
</template>

<script>
  export default {
    asyncData({ payload }) {
      console.log('no payload detected here...')
      console.log(payload)
      if (payload) return { company: payload}
      else {
        return '-1'
      }
    },
    data() {
      return {

      }
    },
    mounted() {
      // console.log(this.$router)
    }
    // async asyncData({ params }) {
    //   const slug = await params.slug
    //   return { slug }
    // },
  }
</script>
