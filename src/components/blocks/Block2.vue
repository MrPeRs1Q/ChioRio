<template>
  <div class="container">
    <div class="content">
      <div class="content__left">
        <p class="step-title">Почему стоит выбрать нас?</p>
      </div>
      <div class="content__right">
        <div v-for="(it, key) in cards" class="content__right__card" :key="key">
          <component :is="it.svg"/>
          <div>
            <p class="card-title">{{ it.title }}</p>
            <p class="card-text">{{ it.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';
import People from '@/assets/icons/people/People.vue';
import Hat from '@/assets/icons/hat/Hat.vue';
import Diplom from '@/assets/icons/diplom/Diplom.vue';

export default {
  name: 'Block2',
  components: {VButton, People, Hat, Diplom},
  data() {
    return {
      cards: [
        {
          svg: 'Hat',
          title: '2020',
          text: 'Преподаём азиатские языки с 2020 года'
        },
        {
          svg: 'People',
          title: '1000+',
          text: 'Учеников прошли обучение в ChioRio'
        },
        {
          svg: 'Diplom',
          title: '>75%',
          text: 'Успешно сдают экзамены на уровни владения языком'
        },
      ]
    };
  },
};
</script>

<style scoped lang="scss">
.container {
  padding: 330px 40px;

  @media(max-width: 800px) {
    padding: 106px 0 122px 0;
  }
}

.content {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));
  grid-gap: 1em;

  &__left {
    max-width: 727px;
    margin: auto 0;
    color: var(--white);

    @media(max-width: 800px) {
      max-width: 500px;
    }

    @media(max-width: 450px) {
      max-width: 324px;
    }
  }

  &__right {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    grid-gap: 1em;
    color: var(--black);

    @media(max-width: 800px) {
      max-width: 335px;
    }

    &__card {
      height: 349px;
      padding: 30px;
      border-radius: 15px;
      background: var(--white);
      display: flex;
      flex-direction: column;
      gap: 75px;

      @media(max-width: 800px) {
        max-width: 335px;
        height: 297px;
      }
    }
  }
}
</style>