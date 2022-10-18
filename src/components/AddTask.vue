<template>
  <form @submit="onSubmit" class="form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task"/>
    </div>
    <div class="form-control">
      <label>Date & Time</label>
      <input type="text" v-model="day" name="text" placeholder="Add Day & Time"/>
    </div>
    <div class="form-control-set">
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="text"/>
    </div>
    <input type="submit" value="Save Task" class="btn"/>
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      text: '',
      day: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if(!this.text) {
        alert('Please add a task')
        return 
      }

      let newTask = {
        id: Math.floor(Math.random() * 1000),
        text: this.text,
        day: this.day,
        reminder: this.reminder
      }
      this.$emit('add-task', newTask)

      this.text = ''
      this.day = ''
      this.reminder = false
    }
  }
  
}

</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin: 10px;
}
.form-control {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-top: 10px;
  font-size: 14px;
  font-weight: 600;
}

.form-control > input {
  margin-top: 10px;
  width: 100%;
  padding: 5px 10px;
}

.form-control-set {
  font-size: 14px;
  font-weight: 600;
  width: 100%;
  padding: 10px 0;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
.form-control-set > input {
  margin-left: 50px;
  width: 15px;
  height: 15px;
}

.btn {
  background-color: #000;
  color: #fff;
  font-size: 16px;
  width: 100%;
  margin: 5px auto;
  padding: 10px 20px;
  cursor: pointer;
}

</style>