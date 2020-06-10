<template>
  <div class="financial">
    <div class="financial__titles">
      <h1>Doar usando ...</h1>
    </div>
    <div class="financial-actions">
      <div>
        <a target="_blank" rel="noopener noreferrer" href="http://picpay.me/guilhermesoares95">
          <Button to="supplies">PicPay</Button>
        </a>
        <span>Com o PicPay você pode fazer sua doação através de cartão de crédito ou saldo de sua carteira.</span>
      </div>
      <div>
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://www.vakinha.com.br/vaquinha/qnq-em-pro-do-colecionando-sorrisos"
        >
          <Button to="financial">Boleto ou Cartão de Crédito</Button>
        </a>
        <span>
          Você será redirecionado para
          <strong>www.vakinha.com.br/</strong>
        </span>
      </div>
      <div>
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://nubank.com.br/pagar/wcpo/NeJU0Hqhmn"
        >
          <Button>Transferência Bancária</Button>
          
        </a>
        <span>
          Você será redirecionado para
          <strong>NuBank</strong>
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
  },
  methods: {
    openLink: function() {
      this.$emit('input', this.$refs.pond.getFiles())
    }
  }
}
</script>

<style lang="scss">
@import 'styles/breakpoints.scss';

.financial {
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

.financial-actions {
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
  .financial {
    &__titles {
      text-align: left;
      h1 {
        margin-bottom: 2rem;
      }
    }
  }
  .financial-actions {
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
  .financial {
    padding: 10rem 1rem 5rem 10rem;
  }
}
</style>

