<template>
  <div class="task-list">
    <upload-form @submitdata="addTask"></upload-form>
    <!--     {{ tasks }} -->
    <task v-for="(t, index) in tasks" :key="index" :task="t">
      {{ t.id }}
    </task>
  </div>
</template>

<script>
import Task from "./Task.vue";
import UploadForm from "./UploadForm.vue";
export default {
  components: { Task, UploadForm },
  data() {
    return {
      loading: true,
      tasks: [],
    };
  },
  mounted() {},
  methods: {
    addTask(value) {
      this.tasks.push(value);
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    finishTask() {},
  },
};
</script>

<style scoped>
.task-list {
  width: 400 px;
  margin: 1rem auto;
}
</style>