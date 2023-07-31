<template>
  <div>
    <div class="d-flex flex-column">
      <div class="d-flex">
        <img src="../assets/icon-list.svg" >
        <p class="small-text mx-5">{{ itemName }}</p>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
defineProps<{
  itemName: String;
}>();
</script>
