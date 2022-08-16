<template>
  <div>
    <Link href="/home">Go Home</Link>
    <h1 class="ext-red-500">Login</h1>
  </div>
</template>

<script>
  import AuthLayout from '../Layouts/Auth.vue' 
  import { Link } from '@inertiajs/inertia-vue3'

  export default {
    components:{
      Link
    },
    layout : AuthLayout
  }
</script>