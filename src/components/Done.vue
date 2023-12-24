<template>
  <h3>DONE</h3>
    <div class="card task pt-2 pb-2 mb-3" v-for="(done, index) in taskDone" :key="index">
      <div class="card-body">
          <div class="row mb-2">
            <h6 for="name">{{ done.name }}</h6>
          </div>
          <div class="row">
            <div class="col-md-4 col-sm-4">
              <p :class="{
                'high': done.priority === 'High', 
                'low': done.priority === 'Low', 
                'medium': done.priority === 'Medium', 
                'p-1': true, 'text-center': true, 'priority': true}">
                  {{ done.priority }}
              </p>
            </div>
            <div class="col-md-8 col-sm-8 space-3 text-md-end text-sm-center">
              <button class="btn btn-danger px-3 mx-1 small"  
                @click="removeDoneList(index)">
                  Delete
                </button>
                <button class="btn btn-warning px-3 mx-2 small" 
                  @click="undoneTask(index)">
                    Undone
                </button>
              </div>
            </div>
        </div>
    </div>

</template>

<script>
  export default {
    props: {
      taskDone: Array,
      removeDoneList: Function,
      undoneTask: Function,
    },
  };
</script>