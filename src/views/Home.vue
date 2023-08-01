<template>
  <div class="container">
    <div :class="{'flex-column-reverse' :mdAndDown}"  class="d-flex" >
      <v-col cols="7" class="main-col">
        <TitleText />
        <ListItem v-for="item in itemData" :item-name="item" />
        <EmailInput class="py-5" />
        <BaseButton title="Subscribe to monthly newsletter" />
      </v-col>
      <v-col cols="5">
        <v-img
          src="../assets/illustration-sign-up-desktop.svg"
          v-if="mdAndUp"
        ></v-img>
        <v-img src="../assets/illustration-sign-up-mobile.svg" v-if="mdAndDown">
        </v-img>
      </v-col>
    </div>
  </div>
</template>

<script lang="ts" setup>
import TitleText from "@/components/TitleText.vue";
import ListItem from "@/components/ListItem.vue";
import EmailInput from "@/components/EmailInput.vue";
import BaseButton from "@/components/BaseButton.vue";
import { useDisplay } from "vuetify";

const { mdAndDown, mdAndUp } = useDisplay();
const itemData = [
  "product discovery and building what matters",
  "Measuring to ensure updates are sucess",
  "And much more!",
];
</script>
<style lang="scss" scoped>
.main-col {
  padding: 4rem 5rem;
}
.container {
  background-color: white;
  width: 70%;
  margin: 10rem auto;
  padding: 0rem 1rem;
  border-radius: 1.5rem;
}
</style>
