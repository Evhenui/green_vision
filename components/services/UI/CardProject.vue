<template>
  <div class="card-project">
    <div class="card-project__wrapper">
      <div class="card-project__image-wrapper">
        <img :src="`/_nuxt/public/img/${img}-card.png`" :alt="img">
      </div>
      <div class="card-project__description">
        <h3 class="card-project__title">{{ title }}</h3>
        <p class="card-project__subtitle">{{ subtitle }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  img: { type: String, required: true },
  title: { type: String, required: true },
  subtitle: { type: String, required: true }
});
</script>

<style lang="scss" scoped>
.card-project {
  --gap: 16px;

  @include set-item-count-in-row(2);

  background-color: white;

  box-shadow: 0px 3px 11px rgba(0, 0, 0, 0.2);
  border-radius: 8px;

  @include bigMobile {
    @include set-item-count-in-row(1);
  }

  &__wrapper {
    @include flex-container(row, space-between, center);

    gap: 8px;
    padding: 43px 80px;

    @include bigMobile {
      @include flex-container(column, center, center);

      gap: 32px;
      padding: 32px 16px;
    }
  }

  &__description {
    max-width: 302px;
    width: 100%;

    @include flex-container(column, flex-start);

    gap: 16px;
  }

  &__title {
    @include font(16, 19, 700);
    text-transform: uppercase;
    color: #1f1f1f;
  }

  &__subtitle {
    @include font(16, 22, 400);
    letter-spacing: 0.02em;
    color: #1f1f1f;
  }
}
</style>
  