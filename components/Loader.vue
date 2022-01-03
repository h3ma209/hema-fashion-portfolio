<template>
  <div class="cont" v-if="loading">
    <div class="circle rounded-full text-center">
      <h1>Loading..</h1>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    loading: false,
  }),
  methods: {
    start() {
      this.loading = true;
    },
    finish() {
      this.loading = false;
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();
      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  },
};
</script>

<style scoped lang="scss">
.cont {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999999999;
  height: 100vh;
  width: 100vw;
  background: black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

  .circle {
    background: olive;
    height: 20vh;
    width: 10vw;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 28px;
    background-color: red;
    animation-name: example;
    animation-duration: 4s;
    animation-iteration-count: 2;
  }
}

@keyframes example {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
