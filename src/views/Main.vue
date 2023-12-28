<template>
  <Page>
    <VHeader/>
    <Block1/>
  </Page>
  <Page variant="dark" center-block>
    <p>Почему стоит выбрать нас</p>
  </Page>
  <Page
      :custom-style="{
        position: 'absolute',
        top: '-149.8px',
        left: '0',
      }"
      center-block
  >
    <template #center>
      <Hieroglyph1/>
    </template>
  </Page>
</template>

<script>
import VHeader from '@/components/VHeader.vue';
import Page from '@/components/Page.vue';
import Logo from '@/assets/icons/logo/Logo.vue';
import Hieroglyph1 from '@/assets/icons/hieroglyphics/hieroglyph1/Hieroglyph1.vue';
import Block1 from '@/components/blocks/Block1.vue';

export default {
  name: 'Main',
  components: {Block1, Hieroglyph1, Logo, Page, VHeader},
};
</script>

<style lang="scss" scoped>

</style>