<template>
  <div>
    <button class="base-btn">{{ title }}</button>
  </div>
</template>
<script lang="ts" setup>
defineProps<{
  title: String;
}>();
</script>

<style lang="scss" scoped>
.base-btn {
  background-color: hsl(234, 29%, 20%);
  padding: 1rem 2rem;
  color: white;
  font-weight: bold;
  border-radius: 5px;
  width: 100%;
}
.base-btn:hover {
  background-image: linear-gradient(
    90deg,
    rgba(255, 84, 119, 1) 0%,
    rgba(255, 102, 68, 1) 73%
  );
  -webkit-box-shadow: 10px 10px 31px 0px rgba(255, 102, 68, 1);
  -moz-box-shadow: 10px 10px 31px 0px rgba(255, 102, 68, 1);
  box-shadow: 10px 10px 31px 0px rgba(255, 102, 68, 1);
}
</style>
