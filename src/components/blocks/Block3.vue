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
  </div>
</template>

<script>
export default {
  name: 'Block3'
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
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));
  grid-gap: 1em;

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
}
</style>