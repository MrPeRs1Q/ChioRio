<template>
  <div class="tab-selector">
    <button
        v-for="(item, key) in tabs" :key="key"
        class="tabs-text tab-selector__tab"
        :class="{ 'tab-selector__tab__active': item.isActive }"
        @click.prevent="clickHandler(item.id)"
    >
      <span>{{ item.title }}</span>
    </button>
  </div>
</template>

<script>
export default {
  name: 'TabSelector',
  props: {
    tabs: { type: Array, required: true },
  },
  methods: {
    clickHandler(id) {
      this.setActiveTabById(id);

      const selectedTab = this.tabs.find((it) => it.id === id);
      this.$emit('selectTab', { ...selectedTab });
    },
    setActiveTabById(id) {
      const clickedIndex = this.tabs.findIndex(((it) => it.id === id));
      this.tabs.forEach((it, index) => {
        it.isActive = index === clickedIndex;
      });
    },
  },
};
</script>

<style scoped lang="scss">
.tab-selector {
  width: 100%;
  display: flex;
  gap: 40px;
  color: var(--black);

  &__tab {
    opacity: 0.6;

    &__active {
      opacity: 1;
      text-decoration: underline;
    }
  }

  @media(max-width: 550px) {
    gap: 20px;
  }
}
</style>