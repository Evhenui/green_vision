<template>
  <section class="begginers">
    <div class="begginers__wrapper">

        <OurOffers 
          class="begginers__offers" 
          :items="offers"
        >
        Что мы предлагаем?
        </OurOffers>

        <InfoOffers
          class="begginers__info-offers"
          :img="infoOffers.img"
          :title="infoOffers.title"
          :subtitle="infoOffers.subtitle"
          :directionLeft="true"
          :button="false"
        />

        <InfoOffers
          class="begginers__info-offers"
          :img="infoOffersB2b.img"
          :title="infoOffersB2b.title"
          :subtitle="infoOffersB2b.subtitle"
          :button="true"
        />

        <InfoOffers
          class="begginers__info-offers"
          :img="infoOffersHotSwap.img"
          :title="infoOffersHotSwap.title"
          :subtitle="infoOffersHotSwap.subtitle"
          :directionLeft="true"
          :button="false"
        />

        <InfoOffers
          class="begginers__info-offers"
          :img="infoOffersGuard.img"
          :title="infoOffersGuard.title"
          :subtitle="infoOffersGuard.subtitle"
          :button="false"
        />

        <OurOffers 
            class="begginers__offers" 
            :items="offersCooperation"
            :submit="true"
        >
        Как начать сотрудничество?
        </OurOffers>

        <ContactUs class="begginers__conacts" :noShadow="true"/>
    </div>
  </section>
</template>

<script setup>
import Promt from "~~/components/common/sections/Promt.vue";
import OurOffers from "~~/components/cooperation/sections/OurOffers.vue";
import InfoOffers from "~~/components/cooperation/sections/InfoOffers.vue";
import UsefulInfo from "~~/components/cooperation/sections/UsefulInfo.vue";
import Suggestions from "~~/components/cooperation/sections/Suggestions.vue";
import ContactUs from "~~/components/common/sections/ContactUs.vue";
import CallBackInfo from "~~/components/common/sections/CallBackInfo.vue";

const offers = [
  {
    title: "Широкий ассортимент и высокая маржинальность товаров до 50% от стоимости.",
    img: "cam",
  },
  {
    title: "Пройти обучение и изучить передовые новинки индустрии видеонаблюдения и контроля доступа. ",
    img: "training",
  },
  {
    title: "Пройти обучение и изучить передовые новинки индустрии видеонаблюдения и контроля доступа. ",
    img: "technical-support",
  },
  {
    title: "Гарантийное и сервисное обслуживание.",
    img: "warranty",
  },
];

const infoOffers = {
  title: "ГИБКАЯ СИСТЕМА СКИДОК И БОНУСОВ",
  subtitle: "Нашими специалистами разработна уникальная бонусная программа, для усиления Вашего бизнеса и увеличения дохода!",
  img: "sale",
};

const infoOffersB2b = {
  title: "Как стать нашим партнером?",
  subtitle: "Оставить заявку на нашем оптовом портале, заполнив все необходимые поля.",
  img: "b2b",
};

const infoOffersHotSwap = {
  title: "Программа 'Горячая замена'",
  subtitle: "Зачем тратить время на выяснения обстоятельств или заказ уже горит, когда Вы работаете на объекте? Специально созданная программа «Горячая замена» включает в себя подменный фонд для оперативной замены оборудования не выезжая с объекта.",
  img: "change-instal",
};

const infoOffersGuard = {
  title: "Защита остатков склада",
  subtitle: "Эксклюзивная программа «Защита остатков склада». Наши друзья и партнеры не должны терять свою прибыль, если стоимость товара внезапно уменьшилась.",
  img: "residue-protection",
};

const offersCooperation = [
  {
    title: "Оставить заявку, заполнив форму обратной связи",
    img: "request",
  },
  {
    title: "После чего наш менеджер свяжется с Вами, для знакомства и уточнения информации.",
    img: "manager",
  },
  {
    title: "Пройти курс обучения монтажу оборудования для видеонаблюдения (по желанию) ",
    img: "traning",
  },
  {
    title: "Получить сертификат",
    img: "certificate",
  },
];


</script>

<style lang="scss" scoped>
.begginers {
  &__wrapper {
    padding: 64px 0 136px 0; 
  }

  &__promt,
  &__info-offers,
  &__suggestions {
    @extend %width-main;

    margin: auto auto 64px auto;
    @extend %padding-wrp;

    @include bigMobile { 
        margin: auto auto 32px auto;
    }
  }

  &__offers {
    @extend %width-main;

    margin: auto auto 32px auto;
    @extend %padding-wrp;
  }

  &__conacts {
    @extend %width-main;

    margin: auto;
    @extend %padding-wrp;
  }

  &__call-back {
    @extend %width-main;

    margin: auto;
    @extend %padding-wrp;
  }
}
</style>