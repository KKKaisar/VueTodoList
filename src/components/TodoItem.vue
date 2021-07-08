<template>
  <li>
    <span :class="{ done: todo.completed }">
      <input
        type="checkbox"
        name=""
        id=""
        @click="todo.completed = !todo.completed"
      />
      <strong>{{ index + 1 }}</strong>
      {{ todo.title | uppercase }}
    </span>
    <button class="rm" @click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number,
  },
  filters: {
    uppercase(value) {
      return value.toUpperCase();
    },
  },
};
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}

.rm {
  background-color: #f00;
  color: #fff;
  border: none;
  font-weight: bold;
  border-radius: 50%;
}

.done {
  text-decoration: line-through;
  font-weight: bold;
}

input {
  margin-right: 1rem;
}
</style>
