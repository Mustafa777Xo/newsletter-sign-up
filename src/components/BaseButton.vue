<template>
  <div>
    <button>{{ title }}</button>
  </div>
</template>
<script lang="ts" setup>
defineProps<{
  title: String;
}>();
</script>
