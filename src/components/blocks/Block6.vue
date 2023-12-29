<template>
  <div class="container">
    <p class="step-title" style="text-align: center; margin-bottom: 40px">Посмотрите, что о нас думают</p>
    <marquee scrolldelay="5">
      <div class="comments">
        <div v-for="(it, key) in comments" class="comments__card" :key="key">
          <div class="comments__card__header">
            <component :is="it.avatar" />
            <div style="display: flex; flex-direction: column; gap: 5px">
              <p class="text" style="font-weight: 700;">{{ it.name }}</p>
              <p class="card-mini-text" style="opacity: 0.6">{{ it.role }}</p>
            </div>
          </div>
          <div class="comments__card__content">
            <p class="text">{{ it.comment }}</p>
          </div>
        </div>
      </div>
    </marquee>
    <marquee v-if="windowSizeForMobile > 800" direction="right" scrolldelay="5">
      <div class="comments">
        <div v-for="(it, key) in comments" class="comments__card" :key="key">
          <div class="comments__card__header">
            <component :is="it.avatar" />
            <div style="display: flex; flex-direction: column; gap: 5px">
              <p class="text" style="font-weight: 700;">{{ it.name }}</p>
              <p class="card-mini-text" style="opacity: 0.6">{{ it.role }}</p>
            </div>
          </div>
          <div class="comments__card__content">
            <p class="text">{{ it.comment }}</p>
          </div>
        </div>
      </div>
    </marquee>
  </div>
</template>

<script>
import Avatar1 from '@/assets/icons/avatar/Avatar1.vue';
import Avatar2 from '@/assets/icons/avatar/Avatar2.vue';

export default {
  name: 'Block6',
  components: {Avatar1, Avatar2},
  data() {
    return {
      windowSizeForMobile: document.documentElement.clientWidth,
      comments: [
        {
          id: 1,
          avatar: 'avatar1',
          name: 'Антон В.',
          role: 'Ученик курсов для поступления в ВУЗ Японии',
          comment: 'Занимаюсь уже 7 месяц, мне очень нравится школа. Школу нашел случайно в интернете. Решил попробовать и не пожалел. Занимаюсь индивидуально онлайн, очень удобно, т.к. я часто нахожусь в разъездах.'
        },
        {
          id: 2,
          avatar: 'avatar2',
          name: 'Влада Н.',
          role: 'Ученица курса китайского с носителем',
          comment: 'Я занимаюсь с преподавателем Чжан Лаоши (носителем китайского языка) уже 4 месяца и просто в восторге! Преподаватель очень интересно и эффективно выстраивает урок, если непонятно какое-либо слово, то объясняет легко и доступно.'
        },
        {
          id: 3,
          avatar: 'Avatar1',
          name: 'Антон В.',
          role: 'Ученик курсов для поступления в ВУЗ Японии',
          comment: 'Занимаюсь уже 7 месяц, мне очень нравится школа. Школу нашел случайно в интернете. Решил попробовать и не пожалел. Занимаюсь индивидуально онлайн, очень удобно, т.к. я часто нахожусь в разъездах.'
        },
        {
          id: 4,
          avatar: 'Avatar2',
          name: 'Влада Н.',
          role: 'Ученица курса китайского с носителем',
          comment: 'Я занимаюсь с преподавателем Чжан Лаоши (носителем китайского языка) уже 4 месяца и просто в восторге! Преподаватель очень интересно и эффективно выстраивает урок, если непонятно какое-либо слово, то объясняет легко и доступно.'
        },
        {
          id: 5,
          avatar: 'Avatar1',
          name: 'Антон В.',
          role: 'Ученик курсов для поступления в ВУЗ Японии',
          comment: 'Занимаюсь уже 7 месяц, мне очень нравится школа. Школу нашел случайно в интернете. Решил попробовать и не пожалел. Занимаюсь индивидуально онлайн, очень удобно, т.к. я часто нахожусь в разъездах.'
        },
        {
          id: 6,
          avatar: 'Avatar2',
          name: 'Влада Н.',
          role: 'Ученица курса китайского с носителем',
          comment: 'Я занимаюсь с преподавателем Чжан Лаоши (носителем китайского языка) уже 4 месяца и просто в восторге! Преподаватель очень интересно и эффективно выстраивает урок, если непонятно какое-либо слово, то объясняет легко и доступно.'
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
.container {
  padding: 295px 40px 100px 40px;
  color: var(--white);

  @media(max-width: 800px) {
    padding: 122px 0 50px 0;
  }
}

.comments {
  display: flex;
  gap: 20px;

  &__card {
    color: var(--black);
    white-space: normal;
    display: flex;
    flex-direction: column;
    gap: 20px;
    background: var(--white);
    border-radius: 25px;
    padding: 30px;
    min-width: 600px;
    max-width: 764px;

    &__header {
      display: flex;
      gap: 20px;
    }

    @media(max-width: 800px) {
      padding: 20px;
      min-width: 323px;
      height: 273px;
    }
  }
}
</style>