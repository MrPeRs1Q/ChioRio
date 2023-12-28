<template>
  <div :class="{['container']: true, [`container--${variant}`]: true}">
    <div v-if="centerBlock" :style="customStyle">
      <slot name="center" />
    </div>
    <div class="container__content">
      <slot/>
    </div>
  </div>
</template>

<script>
import Logo from '@/assets/icons/logo/Logo.vue';

export default {
  name: 'Page',
  components: {Logo},
  props: {
    variant: { type: String, default: 'white' },
    centerBlock: { type: Boolean, default: false },
    customStyle: {type: Object, default: () => ({}) },
  }
};
</script>

<style scoped lang="scss">
.container {
  position: relative;

  &--white {
    background: var(--white);
  }

  &--dark {
    background: var(--black);
  }

  &__content {
    display: flex;
    flex-direction: column;
    gap: 90px;
    padding: 45px 90px;

    @media(max-width: 1000px) {
      padding: 20px;
      gap: 20px;
    }
  }
}
</style>