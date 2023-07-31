<template>
  <div class="container">
    <div class="d-flex">
      <div class="d-flex flex-column">
        <TitleText />
        <ListItem v-for="item in itemData" :item-name="item" />
        <EmailInput />
        <BaseButton title="Subscribe to monthly newsletter" />
      </div>
      <v-img src="../assets/illustration-sign-up-desktop.svg"></v-img>
    </div>
  </div>
</template>

<script lang="ts" setup>
import TitleText from "@/components/TitleText.vue";
import ListItem from "@/components/ListItem.vue";
import EmailInput from "@/components/EmailInput.vue";
import BaseButton from "@/components/BaseButton.vue";

const itemData = [
  "product discovery and building what matters",
  "Measuring to ensure updates are sucess",
  "And much more!",
];
</script>
