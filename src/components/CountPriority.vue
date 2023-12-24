<template>
<div class="row gx-5 mb-2 mt-4">

      <div class="col-md-3 col-sm-12 mb-3">
        <div class="card count" style="width: 100%">
          <div class="card-body text-center">
            <h6 class="card-subtitle mb-2 text-body-secondary">Pending</h6>
            <h5 class="card-title">{{ allTask }}</h5>
          </div>
        </div>
      </div>
      <div class="col-md-3 col-sm-12 mb-3">
        <div class="card count" style="width: 100%">
          <div class="card-body text-center">
            <h6 class="card-subtitle mb-2 text-body-secondary">Low Priority</h6>
            <h5 class="card-title">{{ taskLow }}</h5>
          </div>
        </div>
      </div>
      <div class="col-md-3 col-sm-12 mb-3">
        <div class="card count" style="width: 100%">
          <div class="card-body text-center">
            <h6 class="card-subtitle mb-2 text-body-secondary">Medium Priority</h6>
            <h5 class="card-title">{{ taskMedium }}</h5>
          </div>
        </div>
      </div>
      <div class="col-md-3 col-sm-12 mb-3">
        <div class="card count" style="width: 100%">
          <div class="card-body text-center">
            <h6 class="card-subtitle mb-2 text-body-secondary">High Priority</h6>
            <h5 class="card-title">{{ taskHigh }}</h5>
          </div>
        </div>
      </div>

    </div>

</template>

<script>
export default {
  props: {
    allTask: Number,
    taskLow: Number,
    taskMedium: Number,
    taskHigh: Number,
  },
};
</script>