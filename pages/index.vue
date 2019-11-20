<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex>
      <VVHeroImageContainer class="text-center header-image" :image="image">
        <div class="content">
          <VVLogo class="homepage-logo"/>
          <h1 class="vv-heading where-header">Austin, TX</h1>
          <h1 class="vv-subheading when-header">March 5, 2020</h1>
          <h2 class="vv-subtitle" style="margin-top: 10px;">A one-day conference presented by foxy people who identify as women.</h2>
        </div>
      </VVHeroImageContainer>
      <div class="vv-cta-buttons">
        <VVCtaButton>Register</VVCtaButton>
        <VVCtaButton>Submit a Talk</VVCtaButton>
        <VVCtaButton>Sponsor</VVCtaButton>
        <VVCtaButton>FAQ</VVCtaButton>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import VVHeroImageContainer from '../components/HeroImageContainer';
import VVCtaButton from '../components/CtaButton';
import VVLogo from '../components/Logo';

export default {
  components: {
    VVHeroImageContainer,
    VVCtaButton,
    VVLogo,
  },
  computed: {
    image() {
      return require('../assets/images/austin-city-darken.jpeg');
    }
  }
}
</script>

<style scoped lang="scss">
  .header-image {
    width: 100%;
    height: 60vh;
    color: white;
  }

  .content {
    padding-top: 2vh;
  }

  .homepage-logo {
    $width: 150px;

    width: $width;
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
    margin-bottom: .5rem;
    font-size: 4.2rem;

  }

  .vv-subheading.when-header {
    margin-bottom: 25px;
    font-size: 2.1rem;
  }

  .vv-heading, .vv-subheading {
    &.when-header, &.where-header {
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
</style>
