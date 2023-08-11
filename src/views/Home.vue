<template>
  <!-- desktop -->
  <div v-if="mdAndUp" class="container">
    <div class="d-flex">
      <v-col cols="7" class="main-col">
        <TitleText />
        <ListItem v-for="item in itemData" :item-name="item" />
        <EmailInput class="py-5" />
        <BaseButton
          @click="showOverlay"
          title="Subscribe to monthly newsletter"
        />
      </v-col>
      <v-col cols="5">
        <v-img src="../assets/illustration-sign-up-desktop.svg"></v-img>
      </v-col>
    </div>
  </div>
  <!-- mobile -->
  <div v-if="mdAndDown" class="container">
    <div class="d-flex flex-column">
      <v-row>
        <v-col>
          <v-img
            src="../assets/illustration-sign-up-mobile.svg"
            class="mobile-img"
          />
          <v-container class="pa-5">
            <TitleText />
            <ListItem v-for="item in itemData" :item-name="item" />
            <EmailInput class="py-5" />
            <BaseButton
              @click="showOverlay"
              title="Subscribe to monthly newsletter"
            />
          </v-container>
        </v-col>
      </v-row>
    </div>
  </div>
  <v-overlay v-model="isOverlayVisible">
    <v-container class="overlay-container">
      <v-row>
        <v-col>
          <v-img src="../assets/icon-success.svg" width="5rem"></v-img>
          <p class="big-title mt-8 mb-8">Thank you for subscribing!</p>
          <p class="small-text mb-5" :class="{ 'mb-16': mdAndDown }">
            A confirmation email has been sent to
            <span style="font-weight: bold"> ash@loremcompany.com </span>.
            Please open it and click the button inside to confirm your
            subscription.
          </p>
          <BaseButton title="Dismiss massage" @click="hideOverlay" />
        </v-col>
      </v-row>
    </v-container>
  </v-overlay>
</template>

<script lang="ts" setup>
import TitleText from "@/components/TitleText.vue";
import ListItem from "@/components/ListItem.vue";
import EmailInput from "@/components/EmailInput.vue";
import BaseButton from "@/components/BaseButton.vue";
import { useDisplay } from "vuetify";
import { ref } from "vue";

const { mdAndDown, mdAndUp } = useDisplay();
const itemData = [
  "product discovery and building what matters",
  "Measuring to ensure updates are sucess",
  "And much more!",
];
const isOverlayVisible = ref(false);

const showOverlay = () => {
  isOverlayVisible.value = true;
};

const hideOverlay = () => {
  isOverlayVisible.value = false;
};
</script>
<style lang="scss" scoped>
.main-col {
  padding: 4rem 5rem;
  @media only screen and (max-width: 768px) {
    padding: 2rem 1rem;
  }
}
.container {
  background-color: white;
  width: 70%;
  margin: 10rem auto;
  padding: 0rem 1rem;
  border-radius: 1.5rem;
  @media only screen and (max-width: 768px) {
    width: 100%;
    margin: 0;
    padding: 0;
  }
}
.overlay-container {
  background-color: white;
  margin: 10rem 30rem;
  padding: 5rem;
  border-radius: 1.5rem;
  width: 40%;
  @media only screen and (max-width: 768px) {
    margin: 0;
    padding: 20rem 3rem;
    border-radius: 0;
    width: 100%;
    height: 100vh;
  }
}
</style>
