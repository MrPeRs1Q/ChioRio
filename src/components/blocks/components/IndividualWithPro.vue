<template>
  <div class="content">
    <div class="content__left">
      <p class="text">Рекомендуем индивидуальные занятия с носителем для тех, кто уже имеет небольшую базу в китайском языке или хочет поработать над произношением или разговорной речью.</p>
      <p class="text">Все материалы занятия остаются в личном кабинете, а если вы пропустили урок для вас будет доступна его запись.</p>
      <p class="text">Для занятий необходимо только электронное устройство с доступом в интернет.</p>
      <v-button v-if="windowSizeForMobile > 1670" variant="outlined-dark" style="width: 240px; margin-top: 40px">Оставить заявку</v-button>
    </div>
    <div class="content__right">
      <img v-if="windowSizeForMobile > 800" src="@/assets/images/block5/individual-with-pro.png" alt="mini-group">
      <img v-else src="@/assets/images/block5/individual-with-pro-mobile.png" alt="mini-group">
    </div>
  </div>
  <div class="content__bottom">
    <div v-for="(item, key) in cards" class="content__bottom__card" :key="key">
      <p class="text" style="font-weight: 700">{{ item.lessons }}</p>
      <p class="text">{{ item.description }}</p>
      <div class="content__bottom__card__price">
        <p class="text" style="font-weight: 700; align-self: center; white-space: nowrap">{{ item.price }}</p>
        <p v-if="item.percent" class="card-price-text content__bottom__card__price__percent" style="color: var(--black)">{{ item.percent }}</p>
        <p v-if="item.miniPrice" class="card-price-text" style="opacity: 0.6; align-self: center; white-space: nowrap">{{ item.miniPrice }}</p>
      </div>
    </div>
  </div>
  <v-button v-if="windowSizeForMobile < 1670" variant="outlined-dark" style="width: 240px; margin-top: 30px">Оставить заявку</v-button>
</template>

<script>
import VButton from '@/components/VButton.vue';

export default {
  name: 'IndividualWithPro',
  components: {VButton},
  data() {
    return {
      windowSizeForMobile: document.documentElement.clientWidth,
      cards: [
        {
          lessons: '1 занятие',
          description: 'Понять уровень, и в каком направлении двигаться',
          price: 'Бесплатно',
          percent: null,
          miniPrice: null,
        },
        {
          lessons: '5 занятий',
          description: 'Сделать первые шаги и начать говорить',
          price: '17 500 ₽',
          percent: null,
          miniPrice: '3500 ₽ за урок',
        },
        {
          lessons: '10 занятий',
          description: 'Пополнить словарный запас и начать говорить грамотнее',
          price: '31 500 ₽',
          percent: '-10%',
          miniPrice: '3150 ₽ за урок',
        },
        {
          lessons: '20 занятий',
          description: 'Говорить без ошибок и изучить несколько тем грамматики',
          price: '56 000 ₽',
          percent: '-20%',
          miniPrice: '2800 ₽ за урок',
        },
      ],
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
.content {
  margin-top: 40px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));
  grid-column-gap: 200px;
  grid-row-gap: 150px;

  &__left {
    color: var(--black);
    display: flex;
    flex-direction: column;
    gap: 20px;
    max-width: 820px;

    @media(max-width: 800px) {
      max-width: 335px;
    }
  }

  &__right {
    transform: translateY(-90px);
    max-width: 645px;

    @media(max-width: 800px) {
      max-width: 335px;
    }
  }

  &__bottom {
    overflow-x: auto;
    display: flex;
    gap: 20px;

    &::-webkit-scrollbar {
      width: 0;
    }

    &__card {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 30px;
      background: var(--black);
      border: 1px solid var(--white);
      color: var(--white);
      border-radius: 25px;
      min-width: 410px;
      height: 245px;

      &:first-child {
        background: var(--white);
        border: 1px solid var(--black);
        color: var(--black);
      }

      &__price {
        display: flex;
        gap: 10px;

        &__percent {
          padding: 3px 5px;
          background: var(--white);
          border-radius: 5px;
          align-self: center;
          white-space: nowrap
        }
      }

      @media(max-width: 800px) {
        padding: 20px;
        min-width: 267px;
        height: 205px;
      }
    }
  }
}
</style>