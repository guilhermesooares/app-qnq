<template>
  <div class="container-content">
    <div class="container-content__titles">
      <h1>Obrigado por assistir a live do Quarta no Quarto</h1>
      <p>
        Faça agora sua doação para o grupo
        <strong>Colecionando Sorrisos e nos ajude a ajudar</strong>!
      </p>
    </div>

    <div class="container-content__actions">
      <Button to="donate">Doar agora</Button>
    </div>
  </div>
</template>

<script>
import Button from '~/components/Button'

export default {
  components: {
    Button
  }
}
</script>

<style lang="scss">
@import 'styles/breakpoints.scss';

.container-content {
  &__titles {
    padding-top: 4rem;
    padding-bottom: 5rem;
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
  }
}

@media #{$large-and-up} {
  .container-content {
    &__titles {
      text-align: left;
      h1 {
        margin-bottom: 2rem;
      }
    }

    &__actions {
      .btn {
        max-width: 12.5rem;
      }
    }
  }
}

@media #{$x-large-and-up} {
  .container-content {
    padding: 10rem 1rem 5rem 10rem;
  }
}
</style>

