<template>
    <div class="col-md-3 col-sm-12 mb-3">
        <div class="card count" style="width: 100%">
          <div class="card-body text-center">
            <h6 class="card-subtitle mb-2 text-body-secondary">{{ countName }}</h6>
            <h5 class="card-title">{{ countNumber }}</h5>
          </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    countName: {
      type: String,
      required: true,
    },
    countNumber: {
      type: Number,
      required: true,
    },
  },
};
</script>