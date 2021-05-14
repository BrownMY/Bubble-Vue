<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{ task.text }}</h3>
    <p>{{ task.day }}</p>
    <i @click="onDelete(task.id)" class="fas fa-times"></i>
  </div>
</template>

<script>
export default {
  name: "Task",

  props: {
    task: Object,
  },

  methods: {
    onDelete(id) {
      this.$emit('delete-0tasks', id)
    },
  },
};
</script>

<style scoped>

div {
  display: flex;
  justify-content: space-between;
  padding: 10px;
}

.task {
  background-color: rgb(138, 205, 207);
  margin: 10px;
  color: rgb(233, 248, 255);
  border-radius: 10px;
}

.fas {
  color: tomato;
}

.reminder {
  border-left: 15px solid rgb(84, 166, 168);
}
</style>