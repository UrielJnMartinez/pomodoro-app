<template>
  <section class="welcome">
    <div class="aplication__content welcome__content">
      <h1 class="welcome__title">
        Hola, Bienvenido a Pomodoro!
      </h1>
      <h2 class="welcome__subtitle">
        Mejora tu productividad, centrandote en lo importante de cada mommento.
      </h2>
      <Button @click="onClick()">
        Haz tu primer pomodoro!
      </Button>
    </div>
  </section>
</template>

<script>
import Button from '@/components/Button.vue';
// @ is an alias to /src
export default {
  name: 'Welcome',
  components: {
    Button,
  },
  methods: {
    onClick() {
      // send to page url
      this.$router.push({ name: 'pomodoro', params: { type: 'task' } });
    },
  },
};
</script>

<style lang="scss" scoped>
.welcome{
  background-color: var(--application-color-primary);
}
.welcome__title,
.welcome__subtitle{
  text-align: left;
}
.welcome__content{
  display: flex;
  flex-direction: column;
  // align-items: center;
  justify-content: center;
  color: var(--application-color-text);
}
.welcome__title{
  margin-bottom: 1.2em;
  font-size: 2.5rem;
  font-weight: 500;
  letter-spacing: 1px;
}
.welcome__subtitle{
  font-size: 2rem;
  margin-bottom: 1.2em;
  font-weight: 300;
}
</style>
