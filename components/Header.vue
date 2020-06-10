<template>
  <div class="container__header">
    <nuxt-link to="/">
      <Logo />
    </nuxt-link>
  </div>
</template>

<script>
import Logo from '~/components/Logo'

export default {
  components: {
    Logo
  }
}
</script>