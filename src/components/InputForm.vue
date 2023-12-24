<template>

    <div class="card pt-2 pb-2">
       <div class="card-body align-items-center justify-content-center">
        <form class="row" @submit.prevent="addTaskList">
          <div class="col-md-4 col-sm-12">
            <label for="name">Name</label>
            <input type="text" 
              class="form-control" 
              id="name" 
              placeholder="Input task" 
              style="width:100%" 
              v-model="newTask.name"
              required>
          </div>
          <div class="col-md-4 col-sm-12">
            <label for="inputPassword2" >Priority</label>
            <select class="form-select" 
              aria-label="Input your task" 
              v-model="newTask.priority"
              required>
              <option value="Low">Low</option>
              <option value="Medium">Medium</option>
              <option value="High">High</option>
            </select>
          </div>
          <div class="col-md-4 col-sm-12">
            <button type="submit" class="btn btn-success mt-4" style="width:100%">Save</button>
          </div>
        </form>
      </div>
    </div>
</template>

<script>
export default {
  props: {
    addTaskList: Function,
    newTask: Object,
  }
}
</script>