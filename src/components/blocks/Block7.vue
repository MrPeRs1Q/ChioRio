<template>
  <div>
    <div v-if="windowSizeForMobile > 800" class="container">
      <Hieroglyph4Big/>
      <div class="container__content">
        <div class="container__content__list">
          <Logo/>
          <div style="display: flex; flex-direction: column; gap: 10px">
            <p class="footer-text">Об образовательной организации</p>
            <p class="footer-text">Политика обработки персональных данных</p>
            <p class="footer-text">Договор оферты</p>
          </div>
        </div>
        <div class="container__content__list">
          <p class="text" style="font-weight: 700">Меню</p>
          <div style="display: flex; flex-direction: column; gap: 10px">
            <a class="footer-text" href="#main">Главная</a>
            <a class="footer-text" href="#about">О нас</a>
            <a class="footer-text" href="#prices">Цены</a>
            <a class="footer-text" href="#comments">Отзывы</a>
            <a class="footer-text" href="#contacts">Контакты</a>
          </div>
        </div>
        <div class="container__content__list">
          <p class="text" style="font-weight: 700">Контакты</p>
          <div style="display: flex; flex-direction: column; gap: 10px">
            <a class="footer-text" href="tel: 8 (777) 777 77-77">8 (777) 777 77-77</a>
            <a class="footer-text" href="mailto: info@chiorio.ru">info@chiorio.ru</a>
            <p class="footer-text" style="max-width: 173px; margin-top: 10px">ChioRio — онлайн школа азиатских языков</p>
            <div style="display: flex; gap: 15px; margin-top: 10px">
              <a href="https://vk.com/schoolchiorio" target="_blank"><Vk/></a>
              <a href="https://dzen.ru/chiorio" target="_blank"><Dzen/></a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="container-mobile">
      <div class="container__content">
        <Logo/>
        <div style="display: flex; flex-direction: column; gap: 10px">
          <p class="footer-text">Об образовательной организации</p>
          <p class="footer-text">Политика обработки персональных данных</p>
          <p class="footer-text">Договор оферты</p>
        </div>
      </div>
      <div class="container__content">
        <div>
          <p class="text" style="font-weight: 700">Меню</p>
          <div style="display: flex; flex-direction: column; gap: 10px">
            <a class="footer-text" href="#main">Главная</a>
            <a class="footer-text" href="#about">О нас</a>
            <a class="footer-text" href="#prices">Цены</a>
            <a class="footer-text" href="#comments">Отзывы</a>
            <a class="footer-text" href="#contacts">Контакты</a>
          </div>
        </div>
        <div>
          <p class="text" style="font-weight: 700">Контакты</p>
          <div style="display: flex; flex-direction: column; gap: 10px">
            <a class="footer-text" href="tel: 8 (777) 777 77-77">8 (777) 777 77-77</a>
            <a class="footer-text" href="mailto: info@chiorio.ru">info@chiorio.ru</a>
            <p class="footer-text" style="max-width: 173px; margin-top: 10px">ChioRio — онлайн школа азиатских языков</p>
            <div style="display: flex; gap: 15px; margin-top: 10px">
              <a href="https://vk.com/schoolchiorio" target="_blank"><Vk/></a>
              <a href="https://dzen.ru/chiorio" target="_blank"><Dzen/></a>
            </div>
          </div>
        </div>
      </div>
      <Hieroglyph4/>
    </div>
    <v-divider style="margin: 30px 0"/>
    <div style="display: flex; justify-content: space-between">
      <p class="footer-text">©️2023 «Chio Rio»</p>
      <p class="footer-text">Made by Artyom Babich</p>
    </div>
  </div>
</template>

<script>
import Hieroglyph4 from '@/assets/icons/hieroglyphics/hieroglyph4/Hieroglyph4.vue';
import Hieroglyph4Big from '@/assets/icons/hieroglyphics/hieroglyph4/Hieroglyph4Big.vue';
import Logo from '@/assets/icons/logo/Logo.vue';
import Dzen from '@/assets/icons/dzen/Dzen.vue';
import Vk from '@/assets/icons/vk/Vk.vue';
import VDivider from '@/components/VDivider.vue';

export default {
  name: 'Block7',
  components: {VDivider, Vk, Dzen, Logo, Hieroglyph4Big, Hieroglyph4},
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

<style scoped lang="scss">
.container {
  display: flex;
  gap: 72px;
  padding: 100px 40px 30px 40px;
  color: var(--black);

  &__content {
    display: flex;
    gap: 100px;

    &__list {
      display: flex;
      flex-direction: column;
      gap: 30px;
    }
  }
}

.container-mobile {
  display: flex;
  flex-direction: column;
  gap: 40px;
  padding: 50px 0 20px 0;
  color: var(--black);

  &__content {
    display: flex;
    justify-content: space-between;
  }
}
</style>