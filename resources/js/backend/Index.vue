<template>
  <side-bar></side-bar>
  <v-main class="index">
    <section class="py-10 px-5">
      <v-row>
        <v-col cols="6">
          <v-btn size="large" class="bg-red-darken-3 btn-insert"
            ><i class="mdi mdi-text-box-plus-outline"></i> INSERT</v-btn
          >
        </v-col>
        <v-col cols="6">
          <v-text-field
            :loading="loading"
            density="compact"
            variant="solo"
            label="Search templates"
            append-inner-icon="mdi-magnify"
            single-line
            hide-details
            @click:append-inner="onClick"
          ></v-text-field>
        </v-col>
      </v-row>
    </section>
    <section class="px-5">
      <v-card class="pa-5">
        <v-table>
          <thead class="text-uppercase">
            <tr>
              <th class="text-center">No</th>
              <th>Title</th>
              <th class="text-center">Video Link</th>
              <th class="text-center">Actions</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in desserts" :key="item.id">
              <td class="text-center">{{ item.id }}</td>
              <td>{{ item.title }}</td>
              <td class="text-center">{{ item.video }}</td>
              <td class="text-center"></td>
            </tr>
          </tbody>
        </v-table>
      </v-card>
    </section>
  </v-main>
</template>
<script>
export default {
  data() {
    return {
      search: "",
      desserts: [
        {
          id: 1,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 2,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 3,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 4,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 5,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 6,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 7,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 8,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 9,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
        {
          id: 10,
          title: "TEAM BUILDING2020",
          video: "TEAM BUILDING 2020 - LINKINNOVA",
        },
      ],
    };
  },
};
</script>
