<template>
  <section
    class="usefull-info"
    :class="[
      { 'direction-left': leftDirecion },
      { 'direction-right': !leftDirecion },
    ]"
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
  &.direction-left {
    padding-right: 16px;

    @include bigMobile {
      padding: 0 16px;
    }
    .usefull-info__wrapper {
      @include flex-container(row-reverse, space-between, center);

      border-radius: 0px 250px 250px 0px;

      @include bigMobile {
        @include flex-container(column, center, center);

        border-radius: 16px;

        gap: 24px;
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
  }

  &.direction-right {
    padding-left: 16px;

    @include bigMobile {
      padding: 0 16px;
    }
    .usefull-info__wrapper {
      &::after {
        left: 0;

        background-color: var(--color-sky-lightest);
      }

      &::before {
        right: 0;

        background-color: white;
      }
    }

    .usefull-info__image-wrapper {
      flex: 1 0 454px;

      @include bigMobile {
        flex: auto;
      }
    }
  }

  &__wrapper {
    @extend %width-main;

    @include flex-container(row, space-between, center);

    background-color: white;

    border-radius: 250px 0px 0px 250px;

    gap: 96px;
    margin: auto;
    padding: 48px 16px;

    @include bigMobile {
      @include flex-container(column, center, center);

      border-radius: 16px;

      gap: 24px;
      padding: 24px 16px;
    }

    &::after,
    &::before {
      content: "";

      width: 50vw;
      height: 100%;

      position: absolute;
      top: 0;
      z-index: -1;

      @include bigMobile {
        display: none;
      }
    }
  }

  &__image-wrapper {
    flex: 1 0 537px;

    @include bigMobile {
      flex: auto;
    }
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
}
</style>