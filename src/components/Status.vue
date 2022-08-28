<template>
  <div>
    <div class="todos-status">
      <span class="active-todos"> Active: {{ activeTodosCount }} </span>
      <span class="done-todos"> Done: {{ doneTodosCount }} </span>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Status",
  methods: {
    increment() {
      this.$store.dispatch("incrementAsync");
    },
  },
  computed: {
    ...mapGetters(["doneTodosCount", "activeTodosCount"]),
  },
};
</script>

<style scoped>
span {
  font-size: 14px;
  padding: 10px 20px;
  width: 50px;
  appearance: none;
}
</style>
