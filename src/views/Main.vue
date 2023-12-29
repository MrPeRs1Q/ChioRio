<template>
  <Page>
    <VHeader/>
    <Block1 id="main"/>
  </Page>
  <Page
      :custom-style="{
        position: 'absolute',
        top: `${windowSizeForMobile > 550 ? '-725.8px' : '-40.8px'}`,
        left: '90px',
      }"
      variant="dark"
      center-block
  >
    <template #center>
      <img v-if="windowSizeForMobile > 1700" src="@/assets/images/block2/korea.png" alt="korea">
    </template>
    <Block2/>
  </Page>
  <Page
      :custom-style="{
        position: 'absolute',
        top: `${windowSizeForMobile > 550 ? '-149.8px' : '-40.8px'}`,
        left: '0',
      }"
      center-block
  >
    <template #center>
      <Hieroglyph1 v-if="windowSizeForMobile > 550"/>
      <HieroglyphMobileBlack v-else/>
    </template>
    <Block3 id="about"/>
  </Page>
  <Page
      variant="dark"
      :custom-style="{
        position: 'absolute',
        top: `${windowSizeForMobile > 550 ? '-149.8px' : '-40.8px'}`,
        left: '0',
      }"
      center-block
  >
    <template #center>
      <Hieroglyph2 v-if="windowSizeForMobile > 550"/>
      <HieroglyphMobileWhite v-else/>
    </template>
    <Block4/>
  </Page>
  <Page
      :custom-style="{
        position: 'absolute',
        top: `${windowSizeForMobile > 550 ? '-149.8px' : '-40.8px'}`,
        left: '0',
      }"
      center-block
  >
    <template #center>
      <Hieroglyph1 v-if="windowSizeForMobile > 550"/>
      <HieroglyphMobileBlack v-else/>
    </template>
    <Block5 id="prices"/>
  </Page>
  <Page
      variant="dark"
      :custom-style="{
        position: 'absolute',
        top: `${windowSizeForMobile > 550 ? '-149.8px' : '-40.8px'}`,
        left: '0',
      }"
      center-block
  >
    <template #center>
      <Hieroglyph3 v-if="windowSizeForMobile > 550"/>
      <HieroglyphMobileWhite v-else/>
    </template>
    <Block6 id="comments"/>
  </Page>
  <Page>
    <Block7 id="contacts"/>
  </Page>
</template>

<script>
import VHeader from '@/components/VHeader.vue';
import Page from '@/components/Page.vue';
import Logo from '@/assets/icons/logo/Logo.vue';
import Hieroglyph1 from '@/assets/icons/hieroglyphics/hieroglyph1/Hieroglyph1.vue';
import Hieroglyph2 from '@/assets/icons/hieroglyphics/hieroglyph2/Hieroglyph2.vue';
import Block1 from '@/components/blocks/Block1.vue';
import Block2 from '@/components/blocks/Block2.vue';
import Block3 from '@/components/blocks/Block3.vue';
import HieroglyphMobileBlack from '@/assets/icons/hieroglyphics/hieroglyph-mobile-black/HieroglyphMobileBlack.vue';
import HieroglyphMobileWhite from '@/assets/icons/hieroglyphics/hieroglyph-mobile-white/HieroglyphMobileWhite.vue';
import Block4 from '@/components/blocks/Block4.vue';
import Block5 from '@/components/blocks/Block5.vue';
import Hieroglyph3 from '@/assets/icons/hieroglyphics/hieroglyph3/Hieroglyph3.vue';
import Block6 from '@/components/blocks/Block6.vue';
import Block7 from '@/components/blocks/Block7.vue';

export default {
  name: 'Main',
  components: {
    Block7,
    Block6,
    Hieroglyph3,
    Block5,
    Block4,
    HieroglyphMobileBlack, HieroglyphMobileWhite, Block3, Block2, Block1, Hieroglyph1, Hieroglyph2, Logo, Page, VHeader},
  data() {
    return {
      windowSizeForMobile: document.documentElement.clientWidth,
    };
  },
  mounted() {
    window.addEventListener("resize", this.isMobileHandler);
    this.isMobileHandler();
  },
  destroyed() {
    window.removeEventListener("resize", this.isMobileHandler);
  },
  methods: {
    isMobileHandler() {
      this.windowSizeForMobile = document.documentElement.clientWidth;
    }
  }
};
</script>

<style lang="scss" scoped>

</style>