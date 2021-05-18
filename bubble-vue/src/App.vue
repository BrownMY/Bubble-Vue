<template>
  <div class="container">
    <h1>Bubble</h1>
    <p>Hydration Tracker</p>
    <Header @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask"/>
    <div v-show="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks
      @toggle-reminder="toggleReminder"
      @delete-task="deleteTask"
      :tasks="tasks"
    />
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";
import AddTask from "./components/AddTask";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask,
  },

  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },

    addTask(task) {
      this.tasks = [...this.tasks, task];
    },

    deleteTask(id) {
      if (confirm("Are you sure?"))
        this.tasks = this.tasks.filter((task) => task.id !== id);
    },

    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
  created() {
    this.tasks = [
      {
        id: "1",
        text: "Doctors Appointment",
        day: "March 5th at 2:30pm",
        reminder: true,
      },
      {
        id: "2",
        text: "Meeting with boss",
        day: "March 6th at 1:30pm",
        reminder: true,
      },
      {
        id: "3",
        text: "Food shopping",
        day: "March 7th at 2:00pm",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: rgb(198, 248, 243);
}

.container {
  margin-top: 60px;
  margin: 50px;
}
</style>
