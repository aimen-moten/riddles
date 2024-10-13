<template>
  <div class="center">
    <h1>Riddles Quiz</h1>
    <RiddleForm />
  </div>
</template>

<script>
import RiddleForm from './components/RiddleForm.vue';

export default {
  name: 'App',
  components: {
    RiddleForm
  }
};
</script>
<style scoped>
.center {
  text-align: center;
  background-color: crimson;
}
</style>