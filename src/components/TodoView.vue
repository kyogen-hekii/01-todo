<template>
  <div>
    <input v-model="newItemTitle" type="text" placeholder="please input" @keyup.enter="addTodo"/>
    <button @click="deleteTodo()">del</button>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <label v-bind:class="{ done: todo.isChecked }">
          <input v-model="todo.isChecked" type="checkbox" />{{ todo.title }}
        </label>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newItemTitle: '',
      todos: [
        { id: 1, title: '項目1', isChecked: false },
        { id: 2, title: '項目2', isChecked: false },
        { id: 3, title: '項目3', isChecked: false },
      ],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        title: this.newItemTitle,
        isChecked: false,
      });
      this.newItemTitle = '';
    },
    deleteTodo() {
      this.todos = this.todos.filter(e => e.isChecked === false);
    },
  },
};
</script>

<style lang="sass" scoped>
  li
    list-style: none
    text-align: left
    margin-left: 330px
    display: lineblock
  .done
    text-decoration: line-through

</style>
