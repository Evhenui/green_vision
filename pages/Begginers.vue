<template>
    <section class="begginers">
        <div class="begginers__wrapper">
            <Promt class="begginers__promt">
                Практика показывает, что из многообразия предложений клиент выберет именно того подрядчика, в профессионализме которого у него не возникнет сомнений.
            </Promt>
            <OurOffers class="begginers__offers" :items="offers">Что мы предлагаем?</OurOffers>
            <InfoOffers 
                class="begginers__info-offers"
                :img="infoOffers.img" 
                :title="infoOffers.title"
                :subtitle="infoOffers.subtitle"
                :button="true"
            />
            <UsefulInfo 
                :title="usefullInfo.title"
                :subtitle="usefullInfo.subtitle"
                :img="usefullInfo.img"
                :leftDirecion="true"
            />
        </div>
    </section>
</template>

<script setup>
import Promt from "~~/components/common/sections/Promt.vue";
import OurOffers from "~~/components/cooperation/sections/OurOffers.vue";
import InfoOffers from "~~/components/cooperation/sections/InfoOffers.vue";
import UsefulInfo from "~~/components/cooperation/sections/UsefulInfo.vue";

const offers = [
    {title: 'Пройти обучение и изучить передовые новинки индустрии видеонаблюдения и контроля доступа.', img: 'training'},
    {title: 'Помощь специалистов компании на всех этапах: от составления сметы до ввода готового объекта в эксплуатацию.', img: 'help'},
    {title: 'Квалифицированную техническую и информационную поддержку', img: 'technical-support'},
    {title: 'Гарантийное и послегарантийное обслуживание (оплачивается отдельно)', img: 'warranty'},
]

const infoOffers = {
    title: 'ГИБКАЯ СИСТЕМА СКИДОК И БОНУСОВ',
    subtitle: 'на закупку нашего оборудования (возможность зарабатывать до 50% на разнице цен).',
    img: 'sale'
}

const usefullInfo = {
    title: 'Условия сотрудничества с компанией GreenVision',
    subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ',
    img: 'cooperation'
}
</script>

<style lang="scss" scoped>
.begginers {
    &__wrapper {
    }

    &__promt,
    &__info-offers {
        @extend %width-main;

        margin: auto auto 64px auto;
        @extend %padding-wrp;
    }

    &__offers {
        @extend %width-main;

        margin: auto auto 32px auto;
        @extend %padding-wrp;
    }
}
</style>