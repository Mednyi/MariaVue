<template lang="pug">
header.header
  .logo.header__logo ITTasks
  .panel.header__panel.header__panel_right
    button.button.header__button Попробовать
</template>

<script>
export default {
  name: 'AppHeader',
};
</script>

<style scoped lang="scss">
.header {
  grid-area: h;
  height: 40px;
  background-color: #161616;
  color: #ffffff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 32px;
}
.button {
  border: none;
  padding: 8px;
  background-color: transparent;
  color: white;
  font-size: 16px;
  cursor: pointer;
}
</style>
