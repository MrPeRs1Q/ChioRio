<template>
  <div class="container">
    <div class="content">
      <div class="content__left">
        <p class="title" style="text-transform: uppercase">Онлайн-школа азиатских языков</p>
      </div>
      <div class="content__right">
        <p class="text">Наша образовательная площадка для тех, кто увлечен культурой и традициями азиатских стран. Мы хотим, чтобы у большего количества людей была возможность изучать азиатские языки.</p>
        <v-button style="margin-top: 20px; z-index: 11; position: relative">Попробовать</v-button>
      </div>
    </div>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';

export default {
  name: 'Block1',
  components: {VButton}
};
</script>

<style scoped lang="scss">
.container {
  padding: 0 40px 561px 40px;
  color: var(--black);

  @media(max-width: 800px) {
    padding: 0 0 115px 0;
  }
}

.content {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));
  grid-gap: 1em;

  &__left {
    max-width: 727px;

    @media(max-width: 800px) {
      max-width: 500px;
    }

    @media(max-width: 450px) {
      max-width: 335px;
    }
  }

  &__right {
    max-width: 670px;

    @media(max-width: 800px) {
      max-width: 335px;
    }
  }
}
</style>