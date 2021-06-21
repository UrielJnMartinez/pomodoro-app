<template>
  <section class="timer__display">
    {{minutes}}:{{seconds}}
  </section>
</template>

<script>
export default {
  name: 'Timer',
  props: {
    time: {
      type: Number,
      default: 1200,
    },
  },
  data() {
    return {
      timeInSeconds: 0,
    };
  },
  computed: {
    minutes() {
      const minutes = Math.floor(this.timeInSeconds / 60);
      return this.getPaddedTime(minutes);
    },
    seconds() {
      const seconds = Math.floor(this.timeInSeconds % 60);
      return this.getPaddedTime(seconds);
    },
  },
  mounted() {
    this.setTime(this.$props.time);
    this.startCountDown();
  },
  methods: {
    startCountDown() {
      const countDownTimer = window.setInterval(() => {
        if (!this.timeInSeconds) {
          window.clearInterval(countDownTimer);
          // this.setTime();
          return;
        }

        this.onSecondElapse();
      }, 1000);
    },
    onSecondElapse() {
      this.timeInSeconds -= 1;
    },
    setTime(time) {
      this.timeInSeconds = time;
    },
    getPaddedTime(value) {
      // added 0 in 1 = 01:01
      return value.toString().padStart(2, '0');
    },

  },
  watch: {
    time(time) {
      this.setTime(time);
    },
  },
};
</script>
<style lang="scss" scoped>
</style>
