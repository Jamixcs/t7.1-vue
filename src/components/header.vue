<template>
  <header class="header">
    <div class="header_item" @click="headerItemClick">My Tasks</div>
    <div class="header_item" @click="headerItemClick">In Progress</div>
    <div class="header_item" @click="headerItemClick">Completed</div>
  </header>
</template>
<script setup>
const headerItemClick = (event) => {
  event.target.classList.add("focus");
  // click 之後 要做切換頁面，然後三個不會同時點到
};
</script>
<style lang="scss">
@import "./../assets/sass/base/color";
@import "./../assets/sass/base/font";
@import "./../assets/sass/base/breakpoints";

.header {
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  background-color: $primary-blue;
  @include title;

  @include deviceSize($tablet) {
    flex-direction: row;
    align-items: center;
    gap: 50px;
  }

  &_item {
    flex-basis: 100%;
    text-align: center;
    color: $dark-blue;
    padding: 25px;
    @include deviceSize($tablet) {
      flex-basis: auto;
    }
  }
}

.hover {
  color: $white;
}

.focus {
  box-shadow: inset 0px -5px 0px $dark-blue;
  color: $white;
  font-weight: 500;
}
</style>
