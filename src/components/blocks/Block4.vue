<template>
  <div class="container">
    <div class="content">
      <div class="content__left">
        <p class="step-title">Начните прямо сейчас</p>
        <p class="text" style="opacity: 0.6">Посетите пробный урок и получите скидку 20%</p>
        <ul class="content__left__list">
          <li class="text"><AcceptCircle/><span>Шаг 1: Оставьте заявку</span></li>
          <li class="text"><AcceptCircle/><span>Шаг 2: Посетите бесплатный пробный урок</span></li>
          <li class="text"><AcceptCircle/><span>Шаг 3: Получите скидку на выбранный курс</span></li>
        </ul>
        <v-button v-if="windowSizeForMobile > 1500" style="width: 190px" variant="outlined-white">Записаться</v-button>
      </div>
      <div class="content__right">
        <img v-if="windowSizeForMobile > 850" src="@/assets/images/block4/fudzy.svg" alt="fudzy">
        <img v-else src="@/assets/images/block4/fudzy-mobile.svg" alt="fudzy-mobile">
        <v-button v-if="windowSizeForMobile < 1500" style="width: 190px;" variant="outlined-white">Записаться</v-button>
      </div>
    </div>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';
import AcceptCircle from '@/assets/icons/accept-circle/AcceptCircle.vue';

export default {
  name: 'Block4',
  components: {AcceptCircle, VButton},
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
  padding: 295px 40px 258px 40px;
  color: var(--black);

  @media(max-width: 800px) {
    padding: 122px 0 120px 0;
  }
}

.content {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));
  grid-gap: 1em;

  &__left {
    display: flex;
    flex-direction: column;
    gap: 40px;
    max-width: 610px;
    color: var(--white);

    &__list {
      display: flex;
      flex-direction: column;
      gap: 30px;

      li {
        display: flex;
        align-items: center;
        gap: 40px;
      }
    }

    @media(max-width: 800px) {
      max-width: 500px;
    }

    @media(max-width: 450px) {
      max-width: 335px;
    }
  }

  &__right {
    display: flex;
    flex-direction: column;
    gap: 30px;
    max-width: 860px;

    @media(max-width: 800px) {
      max-width: 335px;
    }
  }
}
</style>