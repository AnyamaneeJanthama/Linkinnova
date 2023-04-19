<template>
    <v-navigation-drawer class="sidesbar" color="#414141" permanent>
        <v-list>
            <router-link to="/Dashboard" class="text-decoration-none">
                <v-list-item
                    prepend-avatar="https://scontent.fcnx3-1.fna.fbcdn.net/v/t1.18169-9/11390156_10203147606931558_337696914167006727_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=09cbfe&_nc_eui2=AeEHgHOKsZF2ku9e2h0SOekf6Yetzn_YjPfph63Of9iM95gfEBsMxVSQEbsmk3NgcvJW9Irs6cHmmbCvcdrCRYDt&_nc_ohc=D8kn_UTrWIgAX_JIQU3&_nc_ht=scontent.fcnx3-1.fna&oh=00_AfDVWlLI9zQOb4RjT0tHJdN0VPom0SF1y6zgd5DzwROX7w&oe=645C4D3E"
                    title="Admin" class="text-white">
                </v-list-item>
            </router-link>
        </v-list>

        <v-divider class="border-opacity-100" color="white"></v-divider>
        <v-list :lines="false" density="compact" nav class="menuadminpanel">
            <!-- <div>
              <router-link to="/Dashboard">
                  <i class="fa-light fa-house"></i>
                  <div>Dashboard</div>
              </router-link>
          </div> -->
            <div>
                <router-link to="/News-and-activitie-end"><i class="fa-light fa-newspaper"></i>
                    <div-title>News & Activities</div-title>
                </router-link>

            </div>
            <div>
                <router-link to="/Current-projects-end"><i class=" fa-light fa-person-digging"></i>
                    <div-title>Current Projects</div-title>
                </router-link>

            </div>
            <div>
                <router-link to="/Completed-projects-end"><i class=" fa-light fa-buildings"></i>
                    <div-title>Completed Projects</div-title>
                </router-link>

            </div>
            <div>
                <router-link to="/Our-partner-end">
                    <i class="fa-light fa-handshake-angle"></i>
                    <div-title>Our Partner</div-title>
                </router-link>

            </div>
            <div>
                <router-link to="/Join-us-end">
                    <i class="fa-light fa-people-group"></i>
                    <div-title>Join us</div-title>
                </router-link>

            </div>
        </v-list>
        <template v-slot:append>
            <div class="pa-2 menuadminpanel">
                <router-link to="/" class="text-decoration-none text-white"> 
                    <i class="fa-light fa-arrow-right-from-bracket"></i>
                    Logout
                </router-link>
            </div>
        </template>
    </v-navigation-drawer>
</template>

<script>
export default {
    data: () => ({
    }),
}
</script>

<style></style>