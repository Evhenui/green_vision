<template>
  <section class="offers">
    <div class="offers__wrapper">
      <h1 class="offers__title">
        <slot></slot>
      </h1>
      <div class="offers__cards">
        <OfferCard 
          v-for="(item, index) in items"
          :key="index"
          :title="item.title"
          :img="item.img"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import OfferCard from '~~/components/cooperation/UI/OfferCard.vue';

defineProps({
  items: { type: Array, required: true },
});
</script>

<style lang="scss" scoped>
.offers {

  &__wrapper {
  }

  &__title {
    @include font(30, 39, 600);
    color: #1F1F1F;
    letter-spacing: 0.02em;
    text-align: center;

    margin-bottom: 24px;
  }

  &__cards {
    @include flex-container(row, flex-start);

    gap: 16px;
  }
}
</style>