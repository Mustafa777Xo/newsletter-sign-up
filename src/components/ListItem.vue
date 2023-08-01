<template>
    <div class="d-flex flex-column">
      <div class="d-flex pb-2">
        <img src="../assets/icon-list.svg" >
        <p class="small-text mx-5">{{ itemName }}</p>
      </div>
    </div>
</template>
<script lang="ts" setup>
defineProps<{
  itemName: String;
}>();
</script>
