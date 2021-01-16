<template>
  <div class="home">
    <div class="logo">
      <img alt="Vue logo" src="../assets/logo.png">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  metaInfo: {
    title: 'Kyron Streetwear',
    titleTemplate: '',
  },
};
</script>

<style lang="scss" scoped>

.home {
  background: no-repeat center/cover;
  background-image: url(../assets/bg.jpg);
  display: flex;
  width: 100%;
  height: 100%;
  position: absolute;
  align-items: center;
  justify-content: center;
}

</style>
