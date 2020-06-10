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
      <nuxt-link to="donate">
        <Button>Doar agora</Button>
      </nuxt-link>
      <a target="_blank" rel="noopener noreferrer" href="https://www.youtube.com/channel/UC34hG4OwyHpgNAQXJ9XVUMw">
        <Button >Acessar a live</Button>
      </a>
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
    padding-top: 3rem;
    padding-bottom: 4rem;
    text-align: center;
    h1 {
      font-weight: 700;
      margin-bottom: 3rem;
    }
  }
  &__actions {
    .btn {
      margin-bottom: 1rem;
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
        margin-right: 1rem;
        max-width: 13rem;
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

