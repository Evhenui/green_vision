<template>
  <div class="offer-card">
    <div class="offer-card__wrapper">
      <div class="offer-card__image-wrapper">
        <img :src="`/_nuxt/public/icons/${img}-offer.svg`" :alt="img" />
      </div>
      <p class="offer-card__title">{{ title }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: { type: String, required: true },
  img: { type: String, required: true }
});
</script>

<style lang="scss" scoped>
.offer-card {
  background-color: white;

  border-radius: 16px;

    &__wrapper {
      @include flex-container(column, center, center);

      gap: 64px;
      padding: 32px;
    }

    &__image-wrapper {
      font-size: 0;
    }

    &__title {
      @include font(18, 25, 500);
      color: #1F1F1F;
      letter-spacing: 0.02em;
      text-align: center;
    }
}
</style>