<template>
  <div class="d-flex flex-column">
    <div class="d-flex justify-space-between">
      <label class="big-title" for="inputField">Email Address</label>
      <p
        v-show="invalidEmail"
        class="big-title"
        style="color: #df4c5f"
        for="inputField"
      >
        Valid email required
      </p>
    </div>
    <input
      type="email"
      id="inputField"
      @input="validateEmail"
      v-model="email"
      class="email-input"
      placeholder="email@company.com"
      :class="{ 'error-input': invalidEmail }"
    />
  </div>
</template>
<script lang="ts" setup>
import { ref } from "vue";

const email = ref<string>("");
const invalidEmail = ref<boolean>(false);

const validateEmail = () => {
  const emailPattern = /^[a-z.-]+@[a-z.-]+\.[a-z]+$/i;

  if (emailPattern.test(email.value)) {
    invalidEmail.value = false;
  } else {
    invalidEmail.value = true;
  }
  console.log(email.value);
  console.log(invalidEmail.value);
};
</script>
<style lang="scss" scoped>
.big-title {
  font-size: 0.8rem;
}
.email-input {
  padding: 1rem;
  border: 2px solid gray;
  border-radius: 0.5rem;
  color: hsl(234, 29%, 20%);
}
.email-input[type="email"]:focus {
  border: 2px solid hsl(235, 18%, 26%);
  outline: none;
  color: hsl(234, 29%, 20%);
}
.error-input[type="email"]:focus {
  background-color: #ffe8e7;
  color: #df4c5f;
  border: 2px solid #df4c5f;
}
</style>
