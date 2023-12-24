<template>
    <h3>TODO</h3>
        <div class="card task pt-2 pb-2 mb-3" v-for="(task, index) in taskList" :key="index">
          <div class="card-body">
              <div class="row mb-2">
                <h6 for="name">{{ task.name }}</h6>
              </div>
              <div class="row">
                <div class="col-md-4 col-sm-4">
                  <p :class="{
                    'high': task.priority === 'High', 
                    'low': task.priority === 'Low', 
                    'medium': task.priority === 'Medium', 
                    'p-1': true, 'text-center': true, 'priority': true}">
                    {{ task.priority }}
                  </p>
                </div>
                <div class="col-md-8 col-sm-8 space-3 text-md-end text-sm-center">
                  <button class="btn btn-danger px-3 mx-1 small" 
                    @click="removeTaskList(index)">
                    Delete
                  </button>
                  <button class="btn btn-success px-3 mx-2 small" 
                    @click="doneTask(index)">
                    Done
                  </button>
              </div>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    props: {
      taskList: Array,
      removeTaskList: Function,
      doneTask: Function,
    },
  };
</script>