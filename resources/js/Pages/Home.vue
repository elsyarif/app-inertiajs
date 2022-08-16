<template>
<Layout>
    <div>
      <Link href="/login"> Login </Link>
      <h1 class="text-red-500">Testing {{ testing }}</h1>
      <n-button>Testing</n-button>
    </div>
    </Layout>
</template>

<script>
  import { Link } from "@inertiajs/inertia-vue3"

  export default {
    props: {
      testing: String
    },

    components: {
      Link
    }
  }
</script>