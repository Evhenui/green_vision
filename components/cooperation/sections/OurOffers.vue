<template>
  <section class="offers" :class="[{ submit: submit }, {short: short}]">
    <div class="offers__wrapper">
      <h1 class="offers__title">
        <slot></slot>
      </h1>
      <div class="offers__cards">
        <OfferCard
          class="offers__card"
          v-for="(item, index) in items"
          :key="index"
          :title="item.title"
          :img="item.img"
          :short="short"
        />
      </div>
      <ButtonGreen class="offers__button">Оставить заявку</ButtonGreen>
    </div>
  </section>
</template>

<script setup>
import OfferCard from "~~/components/cooperation/UI/OfferCard.vue";
import ButtonGreen from "~~/components/common/buttons/ButtonGreen.vue";

defineProps({
  items: { type: Array, required: true },
  submit: { type: Boolean, required: false },
  short: { type: Boolean, required: false },
});
</script>

<style lang="scss" scoped>
.offers {
  &.submit {
    .offers__wrapper {
      @include flex-container(column, center, center);

      gap: 24px;

      @include bigMobile {
        @include flex-container(column, center, stretch);
      }
    }
    .offers__button {
      display: block;

      align-self: center;

      @include bigMobile {
        width: max-content;
      }
    }

    .offers__title {
      margin: 0;
    }
  }

  &.short {
    .offers__cards {
      @include flex-container(row, space-between, center);

      @include bigMobile {
        @include flex-container(column, flex-start, center);

        gap: 8px;
      }
    }
    .offers__card {
      --gap: 78px;

      @include set-item-count-in-row(3);

      @include bigMobile {
        --gap: 8px;

        @include set-item-count-in-row(1);
      }
    }
  }

  &__title {
    @include font(30, 39, 600);
    color: #1f1f1f;
    letter-spacing: 0.02em;
    text-align: center;

    margin-bottom: 24px;

    @include bigMobile {
      @include font(18, 22, 600);
    }
  }

  &__cards {
    @include flex-container(row, flex-start);

    gap: 16px;

    @include bigMobile {
      @include flex-container(column, flex-start, center);

      gap: 8px;
    }
  }

  &__card {
    --gap: 16px;

    @include set-item-count-in-row(4);

    @include bigMobile {
      --gap: 8px;

      @include set-item-count-in-row(1);
    }
  }

  &__button {
    display: none;
  }
}
</style>