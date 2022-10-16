<template>
    <div 
      @dblclick="$emit('toogle-reminder', task.id)"
      :class="[task.reminder ? 'reminder': 'task']"
    >
      <div class="content">
        <h3 class="text">{{task.text}}</h3>
        <p class="day">{{task.day}}</p>
      </div>
      <i @click="$emit('delete-task', task.id)" class="fa fa-times"/>
    </div>

    
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  }
}

</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.reminder {
  border: 1px solid #ccc;
  border-radius: 3px;
  border-left: 6px solid green;
  height: 60px;
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.task {
  border: 1px solid #ccc;
  border-radius: 3px;
  height: 60px;
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.text {
  font-size: 16px;
  
}
.day {
  font-size: 14px;
  margin-top: 5px;
}
.fa {
  cursor: pointer;
}
</style>