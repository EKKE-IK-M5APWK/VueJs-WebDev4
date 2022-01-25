<template>
  <div class="task">
    <h2>{{ task.tile }}</h2>
    <p>Username: {{ task.assigneeId.name }}</p>
    <div>
      {{ task.description }}
    </div>
  </div>
</template>

<script>
export default {
  props: ["task"],
};
</script>