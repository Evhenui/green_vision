<template>
  <section class="begginers">
    <div class="begginers__wrapper">
        <Promt class="begginers__promt" :noShadow="true">
            Практика показывает, что из многообразия предложений клиент выберет
            именно того подрядчика, в профессионализме которого у него не возникнет
            сомнений.
        </Promt>

        <OurOffers class="begginers__offers" :items="offers"
        >Что мы предлагаем?
        </OurOffers>

        <InfoOffers
            class="begginers__info-offers"
            :img="infoOffers.img"
            :title="infoOffers.title"
            :subtitle="infoOffers.subtitle"
            :button="true"
        />

        <UsefulInfo
            class="begginers__useful-info cooperation"
            :title="usefullCooperation.title"
            :subtitle="usefullCooperation.subtitle"
            :img="usefullCooperation.img"
            :leftDirecion="true"
        />

        <UsefulInfo
            class="begginers__useful-info professional"
            :title="usefullProfessional.title"
            :subtitle="usefullProfessional.subtitle"
            :img="usefullProfessional.img"
            :leftDirecion="false"
        />

        <OurOffers 
            class="begginers__offers" 
            :items="offersCooperation"
            :submit="true"
        >
        Как начать сотрудничество?
        </OurOffers>

        <InfoOffers
            class="begginers__info-offers"
            :img="infoOffersGuard.img"
            :title="infoOffersGuard.title"
            :subtitle="infoOffersGuard.subtitle"
            :button="false"
        />

        <Suggestions
          class="begginers__suggestions"
          :img="suggestions.img"
          :title="suggestions.title"
          :subtitle="suggestions.subtitle"
          :link="suggestions.link"
          :directionLeft="false"
        />

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

const offers = [
  {
    title:
      "Пройти обучение и изучить передовые новинки индустрии видеонаблюдения и контроля доступа.",
    img: "training",
  },
  {
    title:
      "Помощь специалистов компании на всех этапах: от составления сметы до ввода готового объекта в эксплуатацию.",
    img: "help",
  },
  {
    title: "Квалифицированную техническую и информационную поддержку",
    img: "technical-support",
  },
  {
    title:
      "Гарантийное и послегарантийное обслуживание (оплачивается отдельно)",
    img: "warranty",
  },
];

const infoOffers = {
  title: "ГИБКАЯ СИСТЕМА СКИДОК И БОНУСОВ",
  subtitle:
    "на закупку нашего оборудования (возможность зарабатывать до 50% на разнице цен).",
  img: "sale",
};

const usefullCooperation = {
  title: "Условия сотрудничества с компанией GreenVision",
  subtitle:
    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
  img: "cooperation",
};

const usefullProfessional = {
  title: "Профессиональный монтажник систем видеонаблюдения",
  subtitle:
    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
  img: "professinal",
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

const infoOffersGuard = {
  title: "Защита остатков склада",
  subtitle: "Эксклюзивная программа «Защита остатков склада». Наши друзья и партнеры не должны терять свою прибыль, если стоимость товара внезапно уменьшилась.",
  img: "residue-protection",
};

const suggestions = {
  img: "estimate",
  title: "Просчет сметы",
  subtitle: "Наша компания предоставляет услуги просчета сметы объекта. Сумма просчета сметы зависит от сложности объекта и количества оборудования.",
  link: "Начни зарабатывать с GreenVision! GreenVision – это просто!"
};

</script>

<style lang="scss" scoped>
.begginers {
  &__wrapper {
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

  &__useful-info {
    margin-bottom: 64px;

    @include bigMobile { 
        padding: 0 16px;
        margin-bottom: 32px;

        &.professional {
            margin-bottom: 54px;
        }
    }
  }

  &__conacts {
    @extend %width-main;

    margin: auto;
    @extend %padding-wrp;
  }
}
</style>