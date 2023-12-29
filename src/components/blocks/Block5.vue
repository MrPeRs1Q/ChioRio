<template>
  <div class="container">
    <p class="step-title" style="margin-bottom: 60px">Цены</p>
    <tab-selector
        :tabs="tabs"
        @selectTab="selectTabHandler"
    />
    <MiniGroup v-if="selectedTab === 'miniGroup'"/>
    <Individual v-if="selectedTab === 'individual'"/>
    <IndividualWithPro v-if="selectedTab === 'individualWithPro'"/>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';
import TabSelector from '@/components/TabSelector.vue';
import MiniGroup from '@/components/blocks/components/MiniGroup.vue';
import Individual from '@/components/blocks/components/Individual.vue';
import IndividualWithPro from '@/components/blocks/components/IndividualWithPro.vue';

export default {
  name: 'Block5',
  components: {IndividualWithPro, Individual, MiniGroup, TabSelector, VButton},
  data() {
    return {
      tabs: [
        {
          id: 1,
          title: 'Мини группа',
          value: 'miniGroup',
          isActive: true,
        },
        {
          id: 2,
          title: 'Индивидуальные занятия',
          value: 'individual',
          isActive: false,
        },
        {
          id: 3,
          title: 'Занятие с носителем языка',
          value: 'individualWithPro',
          isActive: false,
        },
      ],
      selectedTab: 'miniGroup',
    };
  },
  methods: {
    selectTabHandler(selectedTab) {
      this.selectedTab = selectedTab.value;
    },
  }
};
</script>

<style scoped lang="scss">
.container {
  padding: 250px 40px 295px 40px;
  color: var(--black);

  @media(max-width: 800px) {
    padding: 0 0 115px 0;
  }
}
</style>