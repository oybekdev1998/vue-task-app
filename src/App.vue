<template>
  <div class="container">
    <Header title="Task Tracker" />
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>
<script>
  import Header from './components/Header.vue'
  import Tasks from './components/Tasks.vue'


  export default {
    data() {
        return {
          tasks: []
        }
    },
    methods: {
      deleteTask(id) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
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
    components: { Header, Tasks }
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
