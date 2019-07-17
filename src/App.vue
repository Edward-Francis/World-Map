<template>
  <v-app>
    <core-header />
    <v-content>
      <router-view />
    </v-content>
    <core-footer />
  </v-app>
</template>

<script>
export default {
  name: "App",
  components: {
    CoreHeader: () => import("@/components/core/Header"),
    CoreFooter: () => import("@/components/core/Footer")
  }
};
</script>
