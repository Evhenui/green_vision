<template>
  <section 
    class="contacts"
    :class="{'no-shadow': noShadow}"
  >
    <div class="contacts__wrapper">
      <div class="contacts__info">
        <h1 class="contacts__title">СВЯЖИТЕСЬ С НАМИ ПРЯМО СЕЙЧАС</h1>
        <p class="contacts__subtitle">
          Чтобы ознакомиться с условиями сотрудничества, стоимостью продукции,
          программой лояльности для постоянных партнеров, а так же подать
          заявку, заполните и отправьте форму, которая находится ниже.
        </p>
      </div>
      <div class="contacts__inputs">
        <form class="contacts__form">
          <div class="contacts__inputs-wrapper">
            <div class="contacts__inputs-section">
              <InputServices 
                class="contacts__input" 
                :placeholder="'Ваше имя'"
                :type="'text'"
              />

              <InputServices 
                class="contacts__input" 
                :placeholder="'Ваш e-mail'"
                :type="'text'"
              />
            </div>
            <div class="contacts__inputs-section">
              <InputServices 
                class="contacts__input" 
                :placeholder="'Ваш e-mail'"
                :type="'phone'"
              />

              <InputServices 
                class="contacts__input" 
                :placeholder="'Город'"
                :type="'text'"
              />
            </div>
          </div>
          <ButtonGreen class="contacts__button" />
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import InputServices from "~~/components/common/inputs/InputServices.vue";
import ButtonGreen from '~~/components/common/buttons/ButtonGreen.vue';

const inputValues = [
  { placeholder: 'Ваше имя', type: 'text' },
  { placeholder: 'Mobile number', type: 'phone' },
  { placeholder: 'Ваш e-mail', type: 'text' },
  { placeholder: 'Город', type: 'text' },
]

defineProps({
  noShadow: { type: Boolean, required: false},
});
</script>

<style lang="scss" scoped>
.contacts {
  &.no-shadow {
    .contacts__wrapper {
      box-shadow: none;
    }
  }

  &__wrapper {
    @include flex-container(row, space-between);

    background-color: white;

    box-shadow: 0px 3px 11px rgba(0, 0, 0, 0.2);
    border-radius: 16px;

    padding: 136px 32px 96px 32px;
    gap: 24px;

    @include smallestScreen {
      @include flex-container(column, flex-start, flex-start);

      padding: 24px 16px;
      gap: 24px;
    }
  }

  &__info {
    max-width: 504px;
    width: 100%;

    @include flex-container(column, flex-start);

    gap: 24px;
  }

  &__title {
    @include font(25, 35, 700);
    letter-spacing: 0.02em;
    text-transform: uppercase;
    color: #009b3e;

    @include bigMobile {
      @include font(18, 22, 600);
    }
  }

  &__subtitle {
    @include font(20, 28, 400);
    letter-spacing: 0.02em;
    color: #1f1f1f;

    @include bigMobile {
      @include font(16, 22, 400);
    }
  }

  &__inputs {
    max-width: 678px;
    width: 100%;
    flex: 1 0 678px;

    @include bigMobile {
      flex: auto;
    }
  }

  &__form {
    @include flex-container(column, flex-start);

    gap: 84px;

    @include bigMobile {
      gap: 24px;
    }
  }

  &__input {
    max-width: 327px;
    width: 100%;

    @include bigMobile {
      max-width: 100%;
    }
  }

  &__inputs-wrapper {
    @include flex-container(row, flex-start, center);
    flex-wrap: wrap;

    gap: 48px 24px;

    @include bigMobile {
      @include flex-container(column, flex-start, flex-start);

      gap: 24px;
    }
  }

  &__inputs-section {
    max-width: 327px;
    width: 100%;

    @include flex-container(column, flex-start);

    gap: 48px;

    @include smallestScreen {
      max-width: 100%;
    }

    @include bigMobile {
      gap: 24px;
    }
  }

  &__button {
    @include smallestScreen {
      max-width: 248px;

      align-self: center;
    }
  }
}
</style>
  