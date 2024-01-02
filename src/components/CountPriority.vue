<template>
  <div class="row gx-5 mb-2 mt-4">
      <CountCard 
        countName="Pending" 
        :countNumber="allTask"
      />
      <CountCard 
        countName="Low Priority" 
        :countNumber="taskLow" 
      />
      <CountCard 
        countName="Medium Priority" 
        :countNumber="taskMedium"
      />
      <CountCard 
        countName="High Priority" 
        :countNumber="taskHigh" 
      />
  </div>
</template>

<script>
import CountCard from './CountCard.vue';

export default {
  components: {
    CountCard,
  },
  props: {
    allTask: {
      type: Number,
      required: true,
    },
    taskLow: {
      type: Number,
      required: true,
    },
    taskMedium: {
      type: Number,
      required: true,
    },
    taskHigh: {
      type: Number,
      required: true,
    },
  },
};
</script>