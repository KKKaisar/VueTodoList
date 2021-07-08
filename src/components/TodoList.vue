<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo, i) of todos"
        :todo="todo"
        :index="i"
        :key="todo.id"
        @remove-todo="RemoveTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    RemoveTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
