<template>
  <div class="home">
    <TodoView/>
  </div>

</template>

<script>
// @ is an alias to /src
import TodoView from '@/components/TodoView.vue';

export default {
  name: 'home',
  components: {
    TodoView,
  },
};
</script>

<style>
  div {
    font-weight: bold;
  }
</style>
