<script>
import AppHeader from "./components/AppHeader.vue";
import AppContent from "./components/AppContent.vue";
import AppBanner from "./components/AppBanner.vue";
import AppList from "./components/AppList.vue";
import AppFooter from "./components/AppFooter.vue";
  export default {
    components: {
      AppHeader,
      AppContent,
      AppBanner,
      AppList,
      AppFooter
    }
  }
</script>

<template>
  <AppHeader />
  <AppContent />
  <AppBanner />
  <AppList />
  <AppFooter />

</template>

<style>
</style>