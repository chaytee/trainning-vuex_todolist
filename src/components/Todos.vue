<template>
  <div class="container">
    <ul class="todos-list">
      <li class="todo-item" v-for="todo in todos" :key="todo.id">
        <span
          class="todo-content"
          :class="{ done: todo.done }"
          @click="markItDone(todo)"
          >{{ todo.text }}</span
        >
        <span class="del-todo" @click="deleteTodo(todo)">Delete</span>
      </li>
    </ul>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "Todos",
  data() {
    return {
      todos: this.$store.state.todos,
    };
  },
  methods: {
    markItDone(todo) {
      this.$store.commit("missionCompleted", todo.id);
    },
    deleteTodo(todo) {
      this.$store.commit("deleteTodo", todo.id);
    },
  },
  computed: {
    ...mapGetters(["doneTodos", "activeTodos"]),
  },
};
</script>

<style lang="sass" scoped>
.container
  width: 80%
  margin: 0 auto

.todos-list
  list-style: none
  text-align: left

.todo-item
  padding: 10px
  cursor: pointer

.todo-content
  font-size: 20px
  line-height: 1.5
  transition: font-weight .5s ease-in-out
  &:hover
    font-weight: bold

.del-todo
  color: #ed8060
  font-size: 14px
  float: right
  &:hover
    color: #f84510
    font-weight: normal

.todos-status
  display: flex
  justify-content: space-around

.done
  text-decoration: line-through
  color: #dadadc
  &:hover
    font-weight: normal
</style>
