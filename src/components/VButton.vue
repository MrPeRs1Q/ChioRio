<template>
  <button
      :class="{
         ['button']: true,
         [`button--${variant}`]: true,
      }"
      :type="type"
      @click="$emit('click')"
  >
    <slot/>
  </button>
</template>

<script>
export default {
  name: 'VButton',
  props: {
    variant: { type: String, default: 'filled-dark' },
    type: { type: String, default: '' },
  },
};
</script>

<style scoped lang="scss">
.button {
  padding: 20px 40px;
  border-radius: 84px;
  font-family: 'Gilroy', sans-serif;
  font-size: 20px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: 0;
  cursor: pointer;

  &--filled-dark {
    background: var(--black);
    color: var(--white);
  }

  &--filled-white {
    background: var(--white);
    color: var(--black);
  }

  &--outlined-dark {
    border: 1px solid var(--black);
    color: var(--black);
  }

  &--outlined-white {
    border: 1px solid var(--white);
    color: var(--white);
  }

  @media(max-width: 800px) {
    padding: 10px 20px;
    font-size: 14px;
    line-height: 17px;
  }
}
</style>