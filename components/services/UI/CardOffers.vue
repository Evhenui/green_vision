<template>
  <div class="card-offer">
    <div class="card-offer__wrapper">
      <div class="card-offer__image-wrapper">
        <img :src="`/_nuxt/public/img/${img}-card.png`" :alt="img">
      </div>
      <h1 class="card-offer__title">{{ title }}</h1>
      <p class="card-offer__subtitle">{{ subtitle }}</p>
      <ButtonDetails />
    </div>
  </div>
</template>

<script setup>
import ButtonDetails from '~~/components/common/buttons/ButtonDetails.vue'

defineProps({
  img: { type: String, required: true},
  title: { type: String, required: true},
  subtitle: { type: String, required: true}
});
</script>

<style lang="scss" scoped>
.card-offer {
  --gap: 16px;

  @include set-item-count-in-row(3);

  position: relative;

  background-color: white;

  box-shadow: 0px 3px 11px rgba(0, 0, 0, 0.2);
  border-radius: 8px;

  @include bigMobile {
    @include set-item-count-in-row(1);
  }

  &__wrapper {
    min-height: 100%;

    @include flex-container(column, flex-start, center);

    padding: 139px 32px 32px 32px;

    @include bigMobile {
      padding: 123px 24px 24px 24px;
    }
  }

  &__image-wrapper {
    max-width: 192px;
    width: 100%;

    position: absolute;
    top: -50%;

    transform: translateY(50%);

    @include bigMobile {
      max-width: 148px;

      transform: translateY(65%);
    }
  }

  &__title {
    @include font(25, 35, 700);
    letter-spacing: 0.02em;
    text-transform: uppercase;
    text-align: center;
    color: black;

    margin-bottom: 16px;

    @include bigMobile {
      @include font(16, 19, 700);
    }
  }

  &__subtitle {
    flex: 1 1 auto;

    @include font(16, 22, 400);
    letter-spacing: 0.02em;
    text-align: center;
    color: black;

    margin-bottom: 32px;
  }
}
</style>
  