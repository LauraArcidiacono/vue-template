<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="firstComponent">
    <h3>You’ve successfully created a project</h3>
  </div>
</template>

<style scoped>
h3 {
  font-size: 1.2rem;
}
</style>
