<template>
  <div class="donate">
    <div class="donate__titles">
      <h1>Qual o tipo da doação?</h1>
    </div>
    <div class="donate-actions">
      <div>
        <nuxt-link to="/financial">
          <Button>Recursos Financeiros</Button>
        </nuxt-link>

        <span>
          Você pode fazer uma doação
          <strong>usando cartão de crédito ou boleto</strong>
        </span>
      </div>
      <div>
        <nuxt-link to="/supplies">
          <Button>Alimentos, roupas e itens de higiene...</Button>
        </nuxt-link>

        <span>
          Você pode doar estes itens e o
          <strong>Colecionando Sorrisos</strong> vai fazer chegar em quem precisa
        </span>
      </div>
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

.donate {
  &__titles {
    padding-top: 3rem;
    padding-bottom: 1rem;
    text-align: center;
    h1 {
      font-weight: 700;
      margin-bottom: 3rem;
    }
  }
}

.donate-actions {
  padding: 0% 15% 0% 15%;
  div {
    text-align: center;
    margin-bottom: 3rem;
  }
  .btn {
    margin-bottom: 0.7rem;
    width: 100%;
  }
}

@media #{$large-and-up} {
  .donate {
    &__titles {
      text-align: left;
      h1 {
        margin-bottom: 2rem;
      }
    }
  }
  .donate-actions {
    display: flex;
    padding: 0rem;
    flex-direction: column;
    div {
      a {
        margin-right: 2rem;
      }
      span {
        text-align: initial;
        align-self: center;
      }
      display: flex;
      margin-bottom: 3rem;
    }
    .btn {
      margin-bottom: 0rem;
      width: 20rem;
    }
  }
}

@media #{$x-large-and-up} {
  .donate {
    padding: 10rem 1rem 5rem 10rem;
  }
}
</style>

