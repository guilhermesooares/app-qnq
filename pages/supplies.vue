<template>
  <div class="supplies">
    <div class="supplies__titles">
      <h1>Digite sua cidade ...</h1>
    </div>
    <div class="form__group field">
      <input
        v-model="city"
        type="input"
        class="form__field"
        placeholder="Cidade"
        name="cidade"
        id="cidade"
        required
      />
      <label for="Cidade" class="form__label">Cidade</label>
    </div>
    <div class="supplies__leaders">
      <div v-for="city in newCities" :key="city.phone">
        <span>
          <strong>Cidade:</strong>
          {{city.city}}
        </span>
        <span>
          <strong>Líder:</strong>
          {{city.leader}}
        </span>
        <span v-if="city.donations">
          <strong>Local para arrecadação de doações:</strong>
          {{city.donations}}
        </span>

        <a
          target="_blank"
          rel="noopener noreferrer"
          :href="`https://api.whatsapp.com/send?phone=${city.phone}&text=Oi ${city.leader}, vim pela live do Quarta no Quarto e gostaria de saber como faço para doar !`"
        >
          <Button>💬 Entrar em contato via WhatsApp</Button>
        </a>
      </div>
      <div class v-if="newCities.length === 0">
        <span>
          Ainda não temos Colecionando Sorrisos em
          <strong>{{city}}</strong>, mas clique no botão abaixo que vamos direcionar sua ajuda.
          <a
            target="_blank"
            rel="noopener noreferrer"
            :href="`https://api.whatsapp.com/send?phone=583899105979&text=Oi Michelle, sou de ${city} e vim pela live do Quarta no Quarto. Gostaria de saber como faço para doar !`"
          >
            <Button>💬 Entrar em contato via WhatsApp</Button>
          </a>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import cities from './leaders'
import Button from '~/components/Button'

export default {
  components: {
    Button
  },
  data() {
    return {
      city: '',
      cities: [
        {
          leader: 'Lucas Souza',
          city: 'Janaúba MG',
          phone: '553892008813',
          donations:
            'Padaria Edicasa - Rua Campina Grande, 549. Bairro: Gameleira ou Hotel Yara - Avenida - Manoel Athayde, 870. Bairro Saudade'
        },

        {
          leader: 'Abner Ritchelly',
          city: 'Francisco Sá - MG',
          phone: '583891205676'
        },

        {
          leader: 'Julia',
          city: 'Várzea da Palma - MG',
          phone: '553888045727',
          donations: 'Avenida Barão do Guicui, 1958'
        },

        {
          leader: 'Beatriz',
          city: 'Buritizeiro - MG',
          phone: '553899330875',
          donations: 'Rua Vereador João Francisco Braga n41'
        },

        {
          leader: 'Beatriz',
          city: 'Montes Claros - MG',
          phone: '553899382728',
          donations: ''
        },

        {
          leader: 'Alexandre',
          city: 'Cacoal - RO',
          phone: '556999138691',
          donations: ''
        },
        {
          leader: 'Nicoly',
          city: 'São João da Ponte - MG',
          phone: '553892009195',
          donations:
            'Mercearia do Gilvan (38)991914160 e armazém do Soares (38)991461144'
        },
        {
          leader: 'Ana Luiza',
          city: 'Belo Horizonte - MG',
          phone: '553183473546',
          donations:
            'Mercearia do Gilvan (38)991914160 e armazém do Soares (38)991461144'
        },
        {
          leader: 'Maria Fernanda',
          city: 'Lontra - MG',
          phone: '553898354285',
          donations: 'Avenida Montes Claros, n° 272 ou 369, Centro'
        },
        {
          leader: 'Carol',
          city: 'São Paulo - SP',
          phone: '5511964777384'
        },
        {
          leader: 'Larissa Quaresma',
          city: 'Bocaiuva - MG',
          phone: '5538999002946',
          donations: 'Rua José Brandão filho 168 Centro ou Supermercado Vieira'
        }
      ]
    }
  },
  computed: {
    newCities: function() {
      const regexp = new RegExp(this.city, 'i')
      return this.cities

        .filter(x => regexp.test(x.city))
        .sort(function(a, b) {
          if (a.city > b.city) {
            return 1
          }
          if (a.city < b.city) {
            return -1
          }
          return 0
        })
    }
  }
}
</script>

<style lang="scss">
@import 'styles/breakpoints.scss';

.supplies {
  &__titles {
    padding-top: 3rem;
    padding-bottom: 1rem;
    text-align: center;
    h1 {
      font-weight: 700;
      margin-bottom: 3rem;
    }
  }
  &__leaders {
    div {
      display: flex;
      flex-direction: column;
      margin-top: 5rem;
      span {
        padding-bottom: 0.8rem;
      }
    }
  }
}

.supplies-actions {
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
  .supplies {
    &__titles {
      text-align: left;
      h1 {
        margin-bottom: 2rem;
      }
    }
  }
  .supplies-actions {
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
  .supplies {
    padding: 10rem 1rem 5rem 10rem;
  }
}

// Form
$primary: #11998e;
$secondary: #38ef7d;
$white: #fff;
$gray: #9b9b9b;
.form__group {
  width: 100%;
  position: relative;
  padding: 15px 0 0;
  margin-top: 10px;
}

.form__field {
  font-family: inherit;
  width: 100%;
  border: 0;
  border-bottom: 2px solid $gray;
  outline: 0;
  font-size: 1.3rem;
  color: $white;
  padding: 7px 0;
  background: transparent;
  transition: border-color 0.2s;

  &::placeholder {
    color: transparent;
  }

  &:placeholder-shown ~ .form__label {
    font-size: 1.3rem;
    cursor: text;
    top: 20px;
  }
}

.form__label {
  position: absolute;
  top: 0;
  display: block;
  transition: 0.2s;
  font-size: 1rem;
  color: $gray;
}

.form__field:focus {
  ~ .form__label {
    position: absolute;
    top: 0;
    display: block;
    transition: 0.2s;
    font-size: 1rem;
    color: $primary;
    font-weight: 700;
  }
  padding-bottom: 6px;
  font-weight: 700;
  border-width: 3px;
  border-image: linear-gradient(to right, $primary, $secondary);
  border-image-slice: 1;
}
/* reset input */
.form__field {
  &:required,
  &:invalid {
    box-shadow: none;
  }
}
</style>

