<template>
  <section 
    class="info-offer"
    :class="{active : button}"
  >
    <div class="info-offer__wrapper">
      <div class="info-offer__image-wrapper">
        <img :src="`/_nuxt/public/img/${img}-info-offer.png`" :alt="img" />
      </div>
      <div class="info-offer__main-info">
        <h1 class="info-offer__title">{{ title }}</h1>
        <p class="info-offer__subtitle">{{ subtitle }}</p>
        <ButtonGreen class="info-offer__button" />
      </div>
    </div>
  </section>
</template>

<script setup>
import ButtonGreen from '~~/components/common/buttons/ButtonGreen.vue'

defineProps({
  img: { type: String, required: true },
  title: { type: String, required: true },
  subtitle: { type: String, required: true },
  button: { type: Boolean, required: true },
});
</script>

<style lang="scss" scoped>
.info-offer {
  background: white;

  border-radius: 16px;

  &.active {
    .info-offer__button {
      display: block;

      @include bigMobile { 
        width: max-content;

        margin: auto;
      }
    }

    .info-offer__title {
      text-transform: none;
    }

    .info-offer__subtitle {
      margin-bottom: 40px;

      @include bigMobile { 
        margin-bottom: 32px;
      }
    }
  }

  &__wrapper {
    @include flex-container(row, flex-start, center);

    padding: 48px;
    gap: 96px;

    @include bigMobile { 
      @include flex-container(column, center, center);

      padding: 24px 16px;
      gap: 32px;
    }
  }

  &__image-wrapper {
  }

  &__main-info {
    max-width: 700px;
    width: 100%;
  }

  &__title {
    @include font(30, 39, 600);
    text-transform: uppercase;
    letter-spacing: 0.02em;
    color: #009B3E;
    
    margin-bottom: 40px;

    @include bigMobile { 
      @include font(18, 22, 600);

      margin-bottom: 16px;
    }
  }

  &__subtitle {
    @include font(20, 28, 400);
    letter-spacing: 0.02em;
    color: #1F1F1F;

    @include bigMobile { 
      @include font(16, 22, 400);
    }
  }

  &__button {
    display: none;
  }
}
</style>