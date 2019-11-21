<template>
  <section>
    <slot name="header"/>
    <a class="twitter-timeline" :href="accountHref">Vue Vixens Day US Tweets - Curated tweets by VueVixensDay</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
  </section>
</template>

<script>
  export default {
    props: { profile: { type: String, required: true } },
    computed: {
      accountHref() {
        return `https://twitter.com/${this.profile}?ref_src=twsrc%5Etfw`
      }
    }
  }
</script>
