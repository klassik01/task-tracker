<template>
  <form @submit="handleSubmit"> 
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task">
    </div>
    
    <div class="form-control">
      <label>Date & Time</label>
      <input type="text" v-model="date" name="date" placeholder="March 24 at 3:00am">
    </div>

    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder">
    </div>

    <input type="submit" value="Save Task" class="btn btn-block">
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: '',
      date: '',
      reminder: true
    }
  }, 
  methods: {
    handleSubmit(e) {
      e.preventDefault()

      if(!this.text) {
        alert('Do well and add a task')
        return
      }

      const newTask = {
        text: this.text,
        date: this.date,
        reminder: this.reminder
      }

      this.$emit('add-task', newTask)

      this.text = ''
      this.date = ''
      this.reminder = false
    }
  },
}
</script>

<style>
.btn-block {
  width: 100%;
}
form {
  margin-bottom: 40px;
}

.form-control {
  margin: 20px 0;
}

.form-control label {
  display: block;
}

.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}

.form-control-check {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.form-control-check label{
  flex: 1;
}

.form-control-check input{
  flex: 2;
  height: 20px;
}
</style>