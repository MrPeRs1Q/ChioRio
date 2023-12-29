<template>
<div :class="{'divider': true, 'divider__dark': dark}"/>
</template>

<script>
export default {
  name: 'VDivider',
  props: {
    dark: { type: Boolean, default: false },
  }
};
</script>

<style scoped lang="scss">
.divider {
  width: 100%;
  border-bottom: 1px solid var(--gray);

  &__dark {
    border-bottom: 1px solid var(--black);
  }
}
</style>