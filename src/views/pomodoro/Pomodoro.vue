<template>
  <section class="pomodoro">
    <div class="pomodoro__content">
      <h2 class="pomodoro__title">Pomodoro</h2>
      <h1 class="pomodoro__type">{{pomodoroType }}</h1>

      <Timer class="pomodoro__timer" :time="pomodoroTime"></Timer>
      <RoundedBotton @click="onClick()">
        Empezar
      </RoundedBotton>
    </div>
  </section>
</template>

<script>
import Timer from '@/components/Timer.vue';
import RoundedBotton from '@/components/RoundedButton.vue';
import PomodoroTypes from './pomodoroTypes';
// @ is an alias to /src
export default {
  name: 'Pomodoro',
  components: {
    Timer,
    RoundedBotton,
  },
  computed: {
    pomodoroType() {
      return this.$route.params.type;
    },
    pomodoroTime() {
      return PomodoroTypes[this.pomodoroType].time;
    },
  },
  methods: {
    onClick() {
      this.$router.push({ name: 'pomodoro', params: { type: 'rest' } });
    },
  },
};
</script>

<style lang="scss" scoped>
.pomodoro{
  background-color: var(--application-color-primary);
  color: var(--application-color-text);
}
.pomodoro__content{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.pomodoro__title{
  margin-top: 3rem;
  margin-bottom: 1.2em;
  font-size: 2rem;
  font-weight: 500;
  letter-spacing: 1px;
}
.pomodoro__type{
  font-size: 2rem;
  margin-bottom: .8em;
  font-size: 3rem;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.pomodoro__timer{
  font-size: 7rem;
  font-weight: 750;
  margin-bottom: 3rem;
}
</style>
