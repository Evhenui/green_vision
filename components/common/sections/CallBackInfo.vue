<template>
  <section class="callback">
    <div class="callback__wrapper">
      <h3 class="callback__title">{{ title }}</h3>
      <ButtonGreen class="callback__button">{{ phone }}</ButtonGreen>
    </div>
  </section>
</template>

<script setup>
import ButtonGreen from "~~/components/common/buttons/ButtonGreen.vue";

defineProps({
  title: { type: String, required: true },
  phone: { type: String, required: true },
});
</script>

<style lang="scss" scoped>
.callback {
  &__wrapper {
    @include flex-container(row, center, center);

    border-radius: 16px;
    background-color: white;

    padding: 32px;
    gap: 62px;

    @include bigMobile {
      @include flex-container(column, center, center);
    }
  }

  &__title {
    @include font(18, 25, 500);
    color: #000000;
    text-transform: uppercase;
    letter-spacing: 0.02em;

    @include bigMobile {
      @include font(16, 19, 700);
      text-align: center;
    }
  }

  &__button {
    width: max-content;
    
    white-space: nowrap;
  }
}
</style>