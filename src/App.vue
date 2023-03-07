<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTasks" title="Task Tracker" :showAddTask="showAddTask" />
    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header"
import Footer from "./components/Footer"

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      showAddTask: false
    }
  },
  methods: {  
    toggleAddTasks() {
      this.showAddTask = !this.showAddTask
    },
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body {
  color: #333;
  padding: 0 16px;
}

.container {
  max-width: 700px;
  margin: 32px auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 24px;
  border-radius: 12px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 16px;

}
</style>
