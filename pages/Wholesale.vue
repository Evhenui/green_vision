<template>
  <section class="begginers">
    <div class="begginers__wrapper">

        <OurOffers 
          class="begginers__offers" 
          :items="offers"
        >
          Основные преимущества сотрудничества:
        </OurOffers>

        <InfoOffers
          class="begginers__info-offers"
          :img="infoOffers.img"
          :title="infoOffers.title"
          :subtitle="infoOffers.subtitle"
          :button="true"
        />

        <Suggestions
          class="begginers__suggestions"
          :img="suggestions.img"
          :title="suggestions.title"
          :subtitle="suggestions.subtitle"
          :directionLeft="true"
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
          :short="true"
        >
          Как начать сотрудничество?
        </OurOffers>

        <CallBackInfo 
          class="begginers__call-back"
          :title="'ПОЛУЧИТЕ БЕСПЛАТНУЮ КОНСУЛЬТАЦИЮ НАШИХ СПЕЦИАЛИСТОВ ПО ТЕЛЕФОНУ '" 
          :phone="'0 800 211 935'" 
        />
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
    title: "Автоматическая выгрузка товаров нашей торговой марки с актуальными фото и описаниями на сайт, как для интернет-магазинов, так и для маркетплейсов.",
    img: "price",
  },
  {
    title: "Логистика. Сотрудничаем со всеми ведущими перевозчиками, 2 отделения на территории нашего склада. Особо крупные заказ доставляем на своем автопарке. ",
    img: "logistics",
  },
  {
    title: "Информационная поддержка. Мы предоставляем своим клиентам: SEO оптимизированные текстовые описания товара, достоверные технические характеристики, реальные фото, видео обзоры.",
    img: "helper",
  },
  {
    title: "Бесплатное обучение для ваших сотрудников. Мы открываем своим партнерам доступ к нашей внутренней обучающий платформе. ",
    img: "training",
  },
];

const infoOffers = {
  title: "Как стать нашим партнером?",
  subtitle: "Оставить заявку на нашем оптовом портале, заполнив все необходимые поля.",
  img: "b2b",
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
  }
];

const infoOffersGuard = {
  title: "Защита остатков склада",
  subtitle: "Эксклюзивная программа «Защита остатков склада». Наши друзья и партнеры не должны терять свою прибыль, если стоимость товара внезапно уменьшилась.",
  img: "residue-protection",
};

const suggestions = {
  img: "online-news",
  title: "Greenvision - это надёжный импортёр",
  subtitle: "Который поддерживает своих партнеров на всех этапах сотрудничества. В нашей команде работают высококвалифицированные технические специалисты. Мы предоставляем вашим клиентам гарантийное и послегарантийное обслуживание нашего оборудования. Высокая маржинальность товаров и широкий ассортимент. Зарабатывайте до 50% от стоимости товара. ",
};

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