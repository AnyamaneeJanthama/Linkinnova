<template>
  <v-navigation-drawer color="grey-darken-2" permanent>
    <v-list>
      <v-list-item
        prepend-avatar="https://scontent.fcnx3-1.fna.fbcdn.net/v/t1.18169-9/11390156_10203147606931558_337696914167006727_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=09cbfe&_nc_eui2=AeEHgHOKsZF2ku9e2h0SOekf6Yetzn_YjPfph63Of9iM95gfEBsMxVSQEbsmk3NgcvJW9Irs6cHmmbCvcdrCRYDt&_nc_ohc=D8kn_UTrWIgAX_JIQU3&_nc_ht=scontent.fcnx3-1.fna&oh=00_AfDVWlLI9zQOb4RjT0tHJdN0VPom0SF1y6zgd5DzwROX7w&oe=645C4D3E"
        title="admin"
        subtitle="admin@gmail.com"
      >
        <template v-slot:append>
          <v-btn size="small" variant="text" icon="mdi-menu-down"></v-btn>
        </template>
      </v-list-item>
    </v-list>

    <v-divider></v-divider>
    <v-list :lines="false" density="compact" nav class="menuadminpanel">
      <v-list-item>
        <router-link to="/Index">
          <i class="fa-light fa-house"></i>
          <v-list-item-title>Dashboard</v-list-item-title>
        </router-link>
      </v-list-item>
      <v-list-item>
        <router-link to="/"
          ><i class="fa-light fa-newspaper"></i>
          <v-list-item-title>News & Activities</v-list-item-title>
        </router-link>
      </v-list-item>
      <v-list-item>
        <router-link to="/"
          ><i class="fa-light fa-person-digging"></i>
          <v-list-item-title>Current Projects</v-list-item-title>
        </router-link>
      </v-list-item>
      <v-list-item>
        <router-link to="/"
          ><i class="fa-light fa-buildings"></i>
          <v-list-item-title>Completed Projects</v-list-item-title>
        </router-link>
      </v-list-item>
      <v-list-item>
        <router-link to="/">
          <i class="fa-light fa-handshake-angle"></i>
          <v-list-item-title>Our Partner</v-list-item-title>
        </router-link>
      </v-list-item>
      <v-list-item>
        <router-link to="/">
          <i class="fa-light fa-people-group"></i>
          <v-list-item-title>Join us</v-list-item-title>
        </router-link>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({}),
};
</script>

<style></style>
