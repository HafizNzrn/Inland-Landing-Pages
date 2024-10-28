<template>
  <v-app style="background-color: gainsboro; min-height: 100vh;">
    <topbar />
    <transition name="fade">
      <topbar_invert v-if="showTopbarInvert" class="fixed-top" />
    </transition>
    <v-main>
      <mainContent id="scrolling-technique-8"/>
    </v-main>
    <botbar />
  </v-app>
</template>

<script>
import topbar from '@/components/layout/header.vue';
import botbar from '@/components/layout/footer.vue';
import mainContent from '@/components/layout/content.vue';
import topbar_invert from '@/components/layout/header_invert.vue';

export default {
  components: {
    topbar,
    botbar,
    mainContent,
    topbar_invert,
  },
  data() {
    return {
      showTopbarInvert: false,
    };
  },
  methods: {
    handleScroll() {
      this.showTopbarInvert = window.scrollY > 10; // Adjust the value as needed
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>

<style scoped>
.fixed-top {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000; 
  height: 100px;
  overflow: hidden;
  transition: height 0.0s ease-in-out;
}

.fade-enter-active, .fade-leave-active {
  transition: height 0.0ms ease-in-out;
}

.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  height: 10px;
}
</style>
