<template>
  <div v-if="windowSizeForMobile > 1000" class="container">
    <img src="@/assets/images/block2/form.png" alt="form">
  </div>
  <div v-else class="container-middle">
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue';

export default {
  name: 'SelectLanguage',
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
  width: 1740px;
  height: 1008px;
  padding: 327px 40px 40px 40px;
  border-radius: 40px;
  background: url("@/assets/images/block2/korea.png") no-repeat center 100%;
}

.container-middle {
  width: 999px;
  height: 549px;
  padding: 327px 40px 40px 40px;
  border-radius: 40px;
  background: url("@/assets/images/block2/korea-middle.png") no-repeat center 100%;
}
</style>