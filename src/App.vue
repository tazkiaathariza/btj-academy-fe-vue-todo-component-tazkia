<script setup>
  import InputForm from './components/InputForm.vue'
  import Title from './components/Title.vue'
  import CountPriority from './components/CountPriority.vue'
  import Done from './components/Done.vue'
  import Task from './components/Task.vue'
</script>

<template>
 <div class="container mt-5 main">

    <Title text="TODO App"></Title>

    <CountPriority
      :allTask= "allTask"
      :taskLow="taskLow"
      :taskMedium="taskMedium"
      :taskHigh="taskHigh"
    />

    <InputForm :addTaskList="addTaskList" :newTask="newTask"/>

    <div class="row my-4">
      <div class="col-md-6">
        <Task 
          :taskList="taskList" 
          :removeTaskList="removeTaskList" 
          :doneTask="doneTask"/>
      </div>
      <div class="col-md-6">
        <Done 
          :taskDone="taskDone" 
          :removeDoneList="removeDoneList" 
          :undoneTask="undoneTask"/>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: { name: "", priority: "" }, // data baru
      taskList: JSON.parse(localStorage.getItem("taskList")) || [ // list data
        { name: "Makan (example)", priority: "High" }, // default
        { name: "Tidur (example)", priority: "Low" },
      ],
      taskDone: JSON.parse(localStorage.getItem("taskDone")) || [ // list data done
        { name: "Main game (example)", priority: "High" },
      ],
    };
  },
  methods:{
    addTaskList() { // add new task to list
      if (this.newTask.name && this.newTask.priority) {
        let newTask = {
          name: this.newTask.name,
          priority: this.newTask.priority,
          finish: false
        }
        this.taskList.push(newTask);
        localStorage.setItem('taskList', JSON.stringify(this.taskList));
        this.newTask = { name: "", priority: "" }; 
      } 
      alert("Add new task is successful!") //  alert if success
    },
    removeTaskList(index){ // delete task at list
      this.taskList.splice(index, 1);
      localStorage.setItem('taskList', JSON.stringify(this.taskList));
    },
    doneTask(index){ // marking task as done
      let task = this.taskList.splice(index, 1);
      this.taskDone.push(task[0]);
      localStorage.setItem('taskDone', JSON.stringify(this.taskDone)); 
      localStorage.setItem('taskList', JSON.stringify(this.taskList));
    },
    removeDoneList(index){ // remove task in done list
      this.taskDone.splice(index, 1);
      localStorage.setItem('taskDone', JSON.stringify(this.taskDone));
    },
    undoneTask(index){ // undone
      let task = this.taskDone.splice(index, 1);
      this.taskList.push(task[0]);
      localStorage.setItem('taskDone', JSON.stringify(this.taskDone)); 
      localStorage.setItem('taskList', JSON.stringify(this.taskList));
    },
  },
  computed: { // to count on things
    allTask() {
      return this.taskList.length;
    },
    taskHigh() {
      let count = this.taskList.filter(task => task.priority === 'High').length;
      return count;
    },
    taskMedium() {
      let count = this.taskList.filter(task => task.priority === 'Medium').length;
      return count;
    },
    taskLow() {
      let count = this.taskList.filter(task => task.priority === 'Low').length;
      return count;
    },
 
  }
}
</script>

<style>

  .main{
    width: 70%
  }

</style>




