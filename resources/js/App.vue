<template>
  <v-app class="position-relative">
    <app-bar v-if="currentPage != 'Login-admin' && currentPage != 'Login-link' && currentPage != 'Check-mail' && currentPage != 'Dashboard' && currentPage != 'News-and-activitie-end' && currentPage != 'Current-projects-end' && currentPage != 'Completed-projects-end' && currentPage != 'Our-partner-end' && currentPage != 'Join-us-end'"></app-bar>
    <ban-ner v-if="currentPage == 'Home'"></ban-ner>
    <side-bar v-if="currentPage == 'Dashboard' || currentPage == 'News-and-activitie-end' || currentPage == 'Current-projects-end' || currentPage == 'Completed-projects-end' || currentPage == 'Our-partner-end' || currentPage == 'Join-us-end'"></side-bar>
    <v-main class="main-container clearfix" id="con-tent">
      <router-view></router-view>
    </v-main>
    <foo-ter v-if="currentPage != 'Login-admin' && currentPage != 'Login-link' && currentPage != 'Check-mail' && currentPage != 'Dashboard' && currentPage != 'News-and-activitie-end' && currentPage != 'Current-projects-end' && currentPage != 'Completed-projects-end' && currentPage != 'Our-partner-end' && currentPage != 'Join-us-end'"></foo-ter>
  </v-app>
</template>

<script>
export default {
  name: "appMain",
  data() {
    return {
      theme: "light",
    };
  },
  mounted() {
    return this.$route.name;
  },
  watch: {
    currentPage(route) {
      console.log(route);
    },
  },
  methods: {
    setTheme(data) {
      if (data) {
        this.theme = data;
      }
    },
  },
  computed: {
    currentPage() {
      console.log(this.$route.name);
      return this.$route.name;
    },
  },
};
</script>
<style scoped>
#con-tent {
  padding: 0;
}
</style>
