<template>
  <section 
    class="usefull-info"
    :class="{left: leftDirecion}"
  >
    <div class="usefull-info__wrapper">
      <div class="usefull-info__image-wrapper">
        <img :src="`/_nuxt/public/img/${img}-usefull-info.png`" :alt="img" />
      </div>
      <div class="usefull-info__main-info">
        <h1 class="usefull-info__title">{{ title }}</h1>
        <p class="usefull-info__subtitle">{{ subtitle }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  title: { type: String, required: true },
  subtitle: { type: String, required: true },
  img: { type: String, required: true },
  leftDirecion: { type: Boolean, required: true },
});
</script>

<style lang="scss" scoped>
.usefull-info {
  position: relative;
  &.left {
    .usefull-info__wrapper {
      @include flex-container(row-reverse, center, center);

      border-radius: 0px 250px 250px 0px;
    }
  }

  &__wrapper {
    @extend %width-main;

    @include flex-container(row, center, center);

    background-color: white;

    border-radius: 250px 0px 0px 250px;

    gap: 96px;
    margin: auto;
    padding: 48px 0 48px 0;

    &::after,
    &::before {
      content: "";

      width: 50vw;
      height: 100%;

      position: absolute;
      top: 0;
      z-index: -1;
    }

    &::after {
      right: 0;

      background-color: var(--color-sky-lightest);
    }

    &::before {
      left: 0;
      
      background-color: white;
    }
  }

  &__image-wrapper {
  }

  &__main-info {
    max-width: 775px;
    width: 100%;

    @include flex-container(column, center, center);

    gap: 24px;
  }

  &__title {
    @include font(30, 39, 600);
    letter-spacing: 0.02em;
    color: #009B3E;
  }

  &__subtitle {
    @include font(20, 28, 400);
    letter-spacing: 0.02em;
    color: #1F1F1F;
  }
}
</style>