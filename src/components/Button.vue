<template>
    <button @click="handleClick" :class="buttonClass">{{ buttonName }}</button>
</template>

<script>
export default {
  inject: ["removeTaskList", "doneTask", "removeDoneList", "undoneTask"],
  props: {
    buttonName: {
      type: String,
      required: true,
    },
    index: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    buttonClass() {
      switch (this.buttonName) {
        case "Delete":
          return "btn btn-danger px-3 mx-1 small";
        case "Done":
          return "btn btn-success px-3 mx-2 small";
        case "Undone":
          return "btn btn-warning px-3 mx-2 small";
        case "Remove":
         return "btn btn-danger px-3 mx-1 small";
        default:
          console.error("Invalid button text");
          return "btn btn-primary";
      }
    },
  },
  methods: {
    handleClick() {
      switch (this.buttonName) {
        case "Delete":
          this.removeTaskList(this.index);
          break;
        case "Done":
          this.doneTask(this.index);
          break;
        case "Undone":
          this.undoneTask(this.index);
          break;
        case "Remove":
          this.removeDoneList(this.index);
          break;
        default:
          console.error("Invalid button text");
      }
    },
  },
};
</script>
