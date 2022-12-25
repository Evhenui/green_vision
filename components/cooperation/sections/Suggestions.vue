<template>
  <div class="suggestions" :class="[{ left: directionLeft }, {link : link}]">
    <div class="suggestions__wrapper">
      <div class="suggestions__image">
        <img :src="`/_nuxt/public/img/${img}.png`" :alt="img" />
      </div>
      <div class="suggestions__main-info">
        <h1 class="suggestions__title">{{ title }}</h1>
        <p class="suggestions__subtitle">{{ subtitle }}</p>
        <a 
          href="#" 
          class="suggestions__link"
          v-if="link"
        >{{ link }}</a>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  img: { type: String, required: true },
  title: { type: String, required: true },
  subtitle: { type: String, required: true },
  directionLeft: { type: Boolean, required: false },
  link: { type: String, required: false },
});
</script>

<style lang="scss" scoped>
.suggestions {
  border-radius: 16px;

  background-color: white;

  &.left {
    .suggestions__wrapper {
      @include flex-container(row-reverse, flex-start, center);

      @include bigMobile {
        @include flex-container(column, flex-start, flex-start);
      }
    }
  }

  &.link {

    .suggestions__main-info {
      max-width: 495px;
    }
    .suggestions__main-info {
      gap: 24px;
    }
  }

  &__wrapper {
    @include flex-container(row, space-between, center);

    padding: 32px;
    gap: 24px;

    @include bigMobile {
      @include flex-container(column, flex-start, flex-start);

      padding: 16px;
      gap: 16px;
    }
  }

  &__main-info {
    max-width: 535px;
    width: 100%;

    @include flex-container(column, flex-start, flex-start);

    gap: 48px;

    @include bigMobile {
      gap: 16px;
    }
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

  &__link {
    @include font(20, 28, 400);
    letter-spacing: 0.02em;
    color: #009b3e;
  }
}
</style>