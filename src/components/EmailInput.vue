<template>
  <div class="d-flex flex-column">
    <label class="big-title" for="inputField">Email Address</label>
    <input
      type="email"
      id="inputField"
      class="email-input"
      placeholder="email@company.com"
    />
  </div>
</template>
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
</style>
