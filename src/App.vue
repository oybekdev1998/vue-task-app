<template>
  <div class="container">
    <Header
      title="Task Tracker"
      @toogle-add-task='toogleAddTask'
      :showAddTask="showAddTask"
    />
    <div v-if="showAddTask">
      <AddTask @add-task='addTask' />
    </div>
    <Tasks
      @toogle-reminder="toogleReminder"
      @delete-task="deleteTask" 
      :tasks="tasks"
    />
  </div>
</template>
<script>
  import Header from './components/Header.vue'
  import Tasks from './components/Tasks.vue'
  import AddTask from './components/AddTask.vue'


  export default {
    data() {
        return {
          tasks: [],
          showAddTask: false
        }
    },
    methods: {
      toogleAddTask() {
        this.showAddTask = !this.showAddTask
      },
      deleteTask(id) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      },
      toogleReminder(id) {
        this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
      },
      addTask(task) {
        this.tasks = [...this.tasks, task]
      }
    },
    created() {
      this.tasks = [
        {
          id: 1,
          text: 'Doctors Appointment',
          day: 'March 1st at 2.30pm',
          reminder: true 
        },
        {
          id: 2,
          text: 'Meeting in School',
          day: 'March 22st at 4.00pm',
          reminder: true 
        },
        {
          id: 3,
          text: 'Food Shopping',
          day: 'March 5st at 3.00pm',
          reminder: false 
        }
      ]
    },
    components: { Header, Tasks, AddTask }
}

</script>
<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  border: 2px solid #333;
  border-radius: 10px;
  box-sizing: border-box;
  width: 400px;
  margin: 0 auto;
  height: 600px;
  overflow: hidden;
}

</style>
