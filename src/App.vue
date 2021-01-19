<template>
  <div id="app">

    <transition name="fade" mode="out-in" appear>
      <router-view/>
    </transition>
  </div>
</template>

<script lang="ts">

export default {
  metaInfo: {
    titleTemplate: '%s | Kyron Streetwear',
    htmlAttrs: {
      lang: 'en',
    },
  },
};

</script>

<style lang="scss">

@import "assets/scss/slots";

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

</style>
