<template>
  <div class="header__wrapper">
    <header class="header">
      <div class="logo">
        <Logo/>
      </div>
      <div v-show="!isBurgerMenu" class="header__navigation">
        <a class="header__navigation__link" href="#main">Главная</a>
        <a class="header__navigation__link" href="#about">О нас</a>
        <a class="header__navigation__link" href="#prices">Цены</a>
        <a class="header__navigation__link" href="#comments">Отзывы</a>
        <a class="header__navigation__link" href="#contacts">Контакты</a>
      </div>
      <div v-show="isBurgerMenu" style="margin: auto 0">
        <button @click="showBurgerMenu"><Burger/></button>
      </div>
    </header>
    <v-divider/>
  </div>
  <div v-if="isShowBurgerMenu" class="burger-menu__wrapper">
    <div class="burger-menu__container">
      <div style="display: flex; flex-direction: column; gap: 24px">
        <div class="burger-menu__header">
          <Logo style="margin: auto 0"/>
          <button style="margin: auto 0" @click="hideBurgerMenu"><Close/></button>
        </div>
        <v-divider/>
      </div>
      <div class="burger-menu__content">
        <div class="burger-menu__content__navigation">
          <a class="burger-menu__content__navigation__link" href="#main" @click="hideBurgerMenu">Главная</a>
          <a class="burger-menu__content__navigation__link" href="#about" @click="hideBurgerMenu">О нас</a>
          <a class="burger-menu__content__navigation__link" href="#prices" @click="hideBurgerMenu">Цены</a>
          <a class="burger-menu__content__navigation__link" href="#comments" @click="hideBurgerMenu">Отзывы</a>
          <a class="burger-menu__content__navigation__link" href="#contacts" @click="hideBurgerMenu">Контакты</a>
        </div>
        <div class="burger-menu__content__information">
          <div class="burger-menu__content__information__left">
            <a class="burger-menu__content__information__text" href="tel: 8 (777) 777 77-77">8 (777) 777 77-77</a>
            <a class="burger-menu__content__information__text" href="mailto: info@chiorio.ru">info@chiorio.ru</a>
          </div>
          <div class="burger-menu__content__information__right">
            <p class="burger-menu__content__information__text" style="max-width: 160px">ChioRio — онлайн школа азиатских языков</p>
            <div style="display: flex; gap: 15px">
              <a href="https://vk.com/schoolchiorio" target="_blank"><Vk/></a>
              <a href="https://dzen.ru/chiorio" target="_blank"><Dzen/></a>
            </div>
          </div>
        </div>
      </div>
      <div class="burger-menu__footer">
        <Hieroglyph4/>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '@/assets/icons/logo/Logo.vue';
import VDivider from '@/components/VDivider.vue';
import Burger from '@/assets/icons/burger/Burger.vue';
import Close from '@/assets/icons/close/Close.vue';
import Hieroglyph4 from '@/assets/icons/hieroglyphics/hieroglyph4/Hieroglyph4.vue';
import Vk from '@/assets/icons/vk/Vk.vue';
import Dzen from '@/assets/icons/dzen/Dzen.vue';

export default {
  name: 'VHeader',
  components: {Dzen, Vk, Hieroglyph4, Close, Burger, VDivider, Logo},
  data() {
    return {
      isShowBurgerMenu: false,
      isBurgerMenu: false,
      windowSizeForBurger: 0,
    };
  },
  mounted() {
    window.addEventListener("resize", this.isBurgerMenuForResize);
    this.isBurgerMenuForResize();
  },
  destroyed() {
    window.removeEventListener("resize", this.isBurgerMenuForResize);
  },
  methods: {
    isBurgerMenuForResize() {
      this.isBurgerMenu = document.documentElement.clientWidth <= 1100;
    },
    showBurgerMenu() {
      this.isShowBurgerMenu = true;
    },
    hideBurgerMenu() {
      this.isShowBurgerMenu = false;
    },
  }
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;

  &__wrapper {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  &__logo {
    align-self: center;
  }

  &__navigation {
    display: flex;
    gap: 24px;

    &__link {
      border: 1px solid black;
      border-radius: 84px;
      padding: 20px 40px;
      font-family: 'Gilroy', sans-serif;
      font-size: 20px;
      font-weight: 500;
      line-height: 24px;
      letter-spacing: 0;
      align-self: center;

      &:hover {
        background: var(--black);
        color: var(--white);
        transition: .3s;
      }
    }
  }
}

.burger-menu {
  &__wrapper {
    position: fixed;
    padding: 20px;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: var(--white);
    display: flex;
    flex-direction: column;
    z-index: 12;
  }

  &__container {
    margin: 0 auto;
  }

  &__header {
    display: flex;
    justify-content: space-between;
  }

  &__content {
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    gap: 50px;

    &__navigation {
      display: flex;
      flex-direction: column;
      gap: 25px;

      &__link {
        font-family: 'Gilroy', sans-serif;
        font-size: 16px;
        font-weight: 500;
        line-height: 19px;
        letter-spacing: 0;
      }
    }

    &__information {
      display: flex;
      gap: 70px;

      &__text {
        font-family: 'Inter', sans-serif;
        font-size: 12px;
        font-weight: 400;
        line-height: 15px;
        letter-spacing: 0;
      }

      &__left {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }

      &__right {
        display: flex;
        flex-direction: column;
        gap: 20px
      };
    }
  }

  &__footer {
    margin-top: 235px;
  }
}
</style>