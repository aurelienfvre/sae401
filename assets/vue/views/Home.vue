<template>
  <CardContainer height="160vh">
    <div class="home-content">
      <p class="title__home">{{ $t('home.explore') }}</p>
    </div>
    <div class="interactive-components-wrapper">
      <HomeFirstGrid class="home-first-grid" />
      <InteractiveButton class="interactive-button" />
      <HomeSecondGrid class="home-second-grid" />
    </div>
    <div class="educational-sections-wrapper">
      <p>
        {{ $t('home.ecolearnIntro') }}
        <span class="color-ocean">{{ $t('home.ecosystems.ocean') }}</span>,
        <span class="color-jungle">{{ $t('home.ecosystems.jungle') }}</span>,
        <span class="color-forest">{{ $t('home.ecosystems.forest') }}</span>,
        <span class="color-desert">{{ $t('home.ecosystems.desert') }}</span>,
        <span class="color-arctic">{{ $t('home.ecosystems.arctic') }}</span>.

      </p>
      <p>
        {{ $t('home.learnFun') }}
      </p>
    </div>
    <div class="play-button-wrapper">
      <PlayButton />
    </div>
  </CardContainer>

  <div class="cards-container">
    <HomeCard
        cardColor="card-color-ocean"
        :imageSrc="imageOcean"
        :title="$t('home.cards.ocean.title')"
        :subtitle="$t('home.cards.ocean.subtitle')"
        titleColor="#D1E2FD"
        subtitleColor="#fff"
        route="/ocean"
        buttonColor="#D1E2FD"
        :buttonText="$t('home.cards.ocean.button')"
        textColor="black"
    />
    <HomeCard
        cardColor="card-color-jungle"
        :imageSrc="imageJungle"
        :title="$t('home.cards.jungle.title')"
        :subtitle="$t('home.cards.jungle.subtitle')"
        titleColor="#C1DD13"
        subtitleColor="#fff"
        route="/jungle"
        buttonColor="#ABF3DE"
        :buttonText="$t('home.cards.jungle.button')"
        textColor="black"
    />
    <HomeCard
        cardColor="card-color-desert"
        :imageSrc="imageDesert"
        :title="$t('home.cards.desert.title')"
        :subtitle="$t('home.cards.desert.subtitle')"
        titleColor="#D88BCA"
        subtitleColor="#000"
        route="/desert"
        buttonColor="#FFE5D8"
        :buttonText="$t('home.cards.desert.button')"
        textColor="black"
    />
    <HomeCard
        cardColor="card-color-arctic"
        :imageSrc="imageArctic"
        :title="$t('home.cards.arctic.title')"
        :subtitle="$t('home.cards.arctic.subtitle')"
        titleColor="#3A7CA3"
        subtitleColor="#000"
        route="/arctic"
        buttonColor="#EDF4FF"
        :buttonText="$t('home.cards.arctic.button')"
        textColor="black"
    />
  </div>

  <Footer />
</template>

<script setup>
import { useI18n } from 'vue-i18n';
import CardContainer from "@/components/CardContainer.vue";
import InteractiveButton from "@/components/InteractiveButton.vue";
import HomeFirstGrid from "@/components/HomeFirstGrid.vue";
import HomeSecondGrid from "@/components/HomeSecondGrid.vue";
import PlayButton from "@/components/PlayButton.vue";
import HomeCard from "@/components/HomeCard.vue";
import Footer from "@/components/Footer.vue";

const { t } = useI18n();

import imageOcean from "@/assets/image-ocean.webp";
import imageJungle from "@/assets/image-jungle.webp";
import imageDesert from "@/assets/image-desert.webp";
import imageArctic from "@/assets/image-artic.webp";

</script>

<style lang="scss" scoped>
$color-ocean: #3a7ca3;
$color-jungle: #25a37e;
$color-forest: #bdd526;
$color-desert: #fdae84;
$color-arctic: #abcdff;

$card-colors: (
    "ocean": #3574d5,
    "jungle": #25a37e,
    "desert": #fdae84,
    "arctic": #d1e2fd
);

.home-content {
  display: flex;
  align-items: center;
  justify-content: center;
}

.interactive-components-wrapper {
  display: flex;
  align-items: start;
  justify-content: flex-start;
}

.home-first-grid,
.interactive-button,
.home-second-grid {
  min-width: 200px;
  margin-right: 20px;
}

.home-second-grid {
  margin-right: 140px;
  position: relative;
  bottom: 5%;
}

.title__home {
  font-size: 2rem;
  text-align: center;
  margin: 4rem 0 6rem;
  font-weight: 300;
  width: 65%;
  line-height: 1.5;
  font-family: "Inter", sans-serif;
}

.educational-sections-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: start;
  margin: 0;

  p {
    width: 32%;
    font-size: 1.5rem;
    margin: 0 8.3rem;
  }
}

.color-ocean { color: $color-ocean; }
.color-jungle { color: $color-jungle; }
.color-forest { color: $color-forest; }
.color-desert { color: $color-desert; }
.color-arctic { color: $color-arctic; }

.play-button-wrapper {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  margin: 3rem auto;
  justify-content: center;
  max-width: 1200px;

  @each $name, $color in $card-colors {
    .card-color-#{$name} {
      background-color: $color;
    }
  }
}

</style>