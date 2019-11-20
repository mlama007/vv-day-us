<template>
  <v-layout justify-center align-center>
    <v-flex>
      <VVHeroImageContainer class="text-center header-image" :image="HEADER_IMAGE">
        <div class="content">
          <VVLogo class="homepage-logo"/>
          <h1 class="vv-heading where-header">Austin, TX</h1>
          <h1 class="vv-subheading when-header">March 5, 2020</h1>
          <h2 class="vv-subtitle" style="margin-top: 10px;">A one-day conference presented by foxy people who identify as women.</h2>
        </div>
      </VVHeroImageContainer>
      <section class="vv-cta-buttons">
        <VVCtaButton link :href="REGISTRATION_URL" target="_blank">Register</VVCtaButton>
        <VVCtaButton link :href="CFP_URL" target="_blank">Submit a Talk</VVCtaButton>
        <VVCtaButton link href="#faq">FAQ</VVCtaButton>
      </section>
      <section class="vv-tweets-embed">
        <h1 :style="{ color: headerColor }">The excitement is building...</h1>
        <h2 :style="{ color: headerColor }">Registration is not open yet. Stay tuned!</h2>
        <a class="twitter-timeline" href="https://twitter.com/VueVixens?ref_src=twsrc%5Etfw">Vue Vixens Day US Tweets - Curated tweets by VueVixensDay</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
      </section>
    </v-flex>
  </v-layout>
</template>

<script>
import VVHeroImageContainer from '../components/HeroImageContainer';
import VVCtaButton from '../components/CtaButton';
import VVLogo from '../components/Logo';
import { REGISTRATION_URL, CFP_URL, HEADER_IMAGE } from '../constants';

export default {
  components: {
    VVHeroImageContainer,
    VVCtaButton,
    VVLogo,
  },
  computed: {
    HEADER_IMAGE: () => HEADER_IMAGE,
    REGISTRATION_URL: () => REGISTRATION_URL,
    CFP_URL: () => CFP_URL,

    // TODO pull from $vuetify theme, or, even better, put in SCSS from Vuetify
    headerColor: () => { return '#34485d' }
  },
}
</script>

<style scoped lang="scss">
  .header-image {
    width: 100%;
    height: 60vh;
    color: #fff;
  }

  .content {
    padding-top: 2vh;
  }

  .homepage-logo {
    $width: 150px;

    width: $width;

    // Offset the fox logo, because the bottom of the Vue triangle should be centered
    // and the fox tail throws it off by 20%
    margin-left: -#{$width * .2};
  }

  .vv-subtitle {
    font-family: "Futura-MediumItalic", "Helvetica Neue", Arial, sans-serif;
    font-style: italic;
    font-weight: 400;
    max-width: 390px;
    font-size: 1.2rem;
    margin: 20px auto 0;
  }

  .vv-heading.where-header {
    font-size: 4.2rem;
  }

  .vv-subheading.when-header {
    font-size: 2.1rem;
  }

  .vv-heading, .vv-subheading {
    &.when-header, &.where-header {
      margin-bottom: 25px;
      font-family: "Futura-CondensedMedium", "Helvetica Neue", Arial, sans-serif;
      font-weight: 400;
      text-transform: uppercase;
    }
  }

  .vv-cta-buttons {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    align-items: center;
    height: 150px;
    max-width: 830px;
    margin: -80px auto 0;
  }

  .vv-tweets-embed {
    max-width: 90vw;
    margin: 20px auto 0;

    @media(max-width: 800px) {}

    @media(min-width: 1200px) {
      max-width: 800px;
    }

    h1 {
      font-size: 2rem;
    }
    h2 {
      font-size: 1.2rem;
    }
  }
</style>
