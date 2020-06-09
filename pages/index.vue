<template>
  <div class="container">
    <div class="container__header">
      <Logo />
    </div>
    <div class="container__content">
      <h1>Obrigado por assistir a live do Quarta no Quarto</h1>
      <p>
        Faça agora sua doação para o grupo
        <strong>Colecionando Sorrisos e nos ajude a ajudar</strong>!
      </p>
    </div>
    <div class="container__actions">
      <Button @click="donate = true">Doar agora</Button>
    </div>
  </div>
</template>

<script>
import Button from '~/components/Button'
import Logo from '~/components/Logo'

export default {
  components: {
    Logo,
    Button
  }
}
</script>

<style lang="scss">
@import url(styles/styles.scss);
@import url(styles/normalize.scss);
@import url(styles/breakpoints.scss);

.container {
  padding: 1.5rem;
}

.container {
  padding: 1.5rem;
  &__header {
    svg {
      width: 6rem;
    }
  }
  &__content {
    padding-top: 25vh;
    text-align: center;
    h1 {
      font-weight: 700;
      margin-bottom: 3rem;
    }
  }
  &__actions {
    .btn {
      width: 100%;
    }
    margin-top: 6rem;
  }
}
</style>

