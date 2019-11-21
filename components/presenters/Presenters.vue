<template>
  <section>
    <slot name="header"/>
    <v-row cols="6" md="2" justify="center">
      <v-col
        v-for="(presenter, idx) in presenters"
        :key="presenter.name"
        :style="styleFor(idx)"
        >
        <VVPresenterCard :presenter="presenter"/>
      </v-col>
    </v-row>
  </section>
</template>

<script>
import { PRESENTERS_DATA } from '../../constants';
import VVPresenterCard from './PresenterCard';

export default {
  components: { VVPresenterCard },
  methods: {
    styleFor(idx) {
      let align = idx === this.presenters.length - 1 ? 'flex-start' : 'center';
      return ` justify-self: ${align}; margin: 20px auto; max-width: 50%`;
    }
  },
  computed: {
    presenters() { return PRESENTERS_DATA; }
  }
}
</script>
