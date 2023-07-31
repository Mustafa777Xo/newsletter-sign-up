<template>
  <div>
    <div class="d-flex flex-column">
      <div class="d-flex">
        <v-img src="../assets/icon-list.svg"></v-img>
        <p>{{ itemName }}</p>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
defineProps<{
  itemName: String;
}>();
</script>
