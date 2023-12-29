<template>
  <div class="container">
    <div class="content">
      <div class="content__left">
        <p class="step-title">Мы прилагаем максимум усилий, чтобы обучение было эффективным</p>
      </div>
      <div class="content__right">
        <p class="text">На пробном уроке преподаватель определит ваш уровень знания языка и поможет подобрать подходящий курс</p>
      </div>
    </div>
    <div class="content__bottom">
      <img v-if="windowSizeForMobile >= 1850" src="@/assets/images/block3/block3-default.svg" alt="block3-default">
      <img v-else src="@/assets/images/block3/block3-mobile.svg" alt="block3-mobile">
    </div>
    <div style="text-align: center">
      <v-button variant="outlined-dark">Записаться</v-button>
    </div>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';

export default {
  name: 'Block3',
  components: {VButton},
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
  padding: 295px 40px 349px 40px;

  @media(max-width: 800px) {
    padding: 122px 0 92px 0;
  }
}

.content {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, auto));
  grid-column-gap: 166px;
  grid-row-gap: 50px;

  &__left {
    max-width: 967px;

    @media(max-width: 800px) {
      max-width: 500px;
    }

    @media(max-width: 450px) {
      max-width: 335px;
    }
  }

  &__right {
    max-width: 566px;

    @media(max-width: 800px) {
      max-width: 335px;
    }
  }

  &__bottom {
    text-align: center;
    margin-top: 90px;
    margin-bottom: 60px;
  }
}
</style>