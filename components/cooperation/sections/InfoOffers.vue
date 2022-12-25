<template>
  <section 
    class="info-offre"
    :class="{active : button}"
  >
    <div class="info-offre__wrapper">
      <div class="info-offre__image-wrapper">
        <img :src="`/_nuxt/public/img/${img}-info-offer.png`" :alt="img" />
      </div>
      <div class="info-offre__main-info">
        <h1 class="info-offre__title">{{ title }}</h1>
        <p class="info-offre__subtitle">{{ subtitle }}</p>
        <ButtonGreen class="info-offre__button" />
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
.info-offre {
  background: white;

  border-radius: 16px;

  &.active {
    .info-offre__button {
      display: block;
    }

    .info-offre__title {
      text-transform: none;
    }

    .info-offre__subtitle {
      margin-bottom: 40px;
    }
  }

  &__wrapper {
    @include flex-container(row, flex-start, center);

    padding: 48px;
    gap: 96px;
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
  }

  &__subtitle {
    @include font(20, 28, 400);
    letter-spacing: 0.02em;
    color: #1F1F1F;

    margin-bottom: 56px;
  }

  &__button {
    display: none;
  }
}
</style>