<template>
  <v-btn v-bind="$attrs" color="secondary" class="vv-button" raised x-large link><slot></slot></v-btn>
</template>

<style scoped lang="scss">
  .vv-button {
    font-family: "Futura-CondensedMedium", "Helvetica Neue", Arial, sans-serif;
    text-transform: initial;
    font-size: 1.7rem;
    letter-spacing: normal;

    /* Bigger buttons than usual. Override specificity of vuetify */
    &.vv-button.vv-button.vv-button {
      padding: 15px 35px;
      height: unset;
    }
  }
</style>
