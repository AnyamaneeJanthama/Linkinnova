<template>
    <div>
        <side-bar></side-bar>
        <v-main>
            <v-row class="ma-1 news-activitie">
                <!-- dialogInsert -->
                <v-dialog v-model="dialoginsert" persistent width="auto">
                    <template v-slot:activator="{ props }">
                        <v-col cols="8" class="d-flex align-end">
                            <v-btn color="#D50703" class="text-white" v-bind="props"><i
                                    class="mdi mdi-text-box-plus-outline"></i>Insert
                            </v-btn>
                        </v-col>
                    </template>
                    <v-card>
                        <v-toolbar class="text-center text-white" color="#D50703"
                            title="INSERT INTO NEWS & ACTIVITIES"></v-toolbar>
                        <v-card-text>
                            <v-container>
                                <v-row class="d-flex align-center">
                                    <v-col cols="2">
                                        <v-list-subheader>Title : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-text-field variant="outlined" required></v-text-field>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Video Name : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-text-field variant="outlined" required></v-text-field>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Description : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-textarea variant="outlined" required></v-textarea>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>YouTube Link : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-text-field variant="outlined" required></v-text-field>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Date Create : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <input type="date" name="date">
                                    </v-col>
                                    <v-col class="d-flex justify-center align-center fileinsert" cols="12" sm="12" md="12">
                                        <label for="myImage"><i class="mdi mdi-image-plus-outline"></i></label>
                                        <input type="file" id="myImage" accept="image/png, image/gif, image/jpeg" />
                                    </v-col>
                                </v-row>
                            </v-container>
                        </v-card-text>
                        <v-card-actions class="d-flex justify-center align-center">
                            <v-btn color="#F9A825" @click="dialoginsert = false">
                                <i class="fa-regular fa-xmark"></i>Cancle
                            </v-btn>
                            <v-btn color="#28A745" @click="dialoginsert = false">
                                <i class="fa-light fa-floppy-disk"></i>Save
                            </v-btn>

                        </v-card-actions>
                    </v-card>
                </v-dialog>
                <!-- dialogInsert END -->
                <v-col cols="3"><v-text-field v-model="search" class="text-red" variant="underlined" label="Search"
                        single-line hide-details></v-text-field>
                </v-col>
                <v-col cols="1" class="d-flex align-end">
                    <i class="fa-solid fa-magnifying-glass iconsearch"></i>
                </v-col>
                <v-col cols="12">
                    <v-card>
                        <v-table>
                            <thead>
                                <tr>
                                    <th>No.</th>
                                    <th>Title</th>
                                    <th>Video Name</th>
                                    <th>Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="item in desserts" :key="item.id">
                                    <td>{{ item.id }}</td>
                                    <td>{{ item.title }}</td>
                                    <td>{{ item.videoname }}</td>
                                    <td>
                                        <!-- dialogView -->
                                        <v-btn color="#00D1FF" class="text-white" @click="dialogview = true">
                                            <i class="fa-solid fa-eye"></i>
                                        </v-btn>
                                        <!-- dialogView END -->
                                        <!-- dialogEdit -->
                                        <v-btn color="#F9A825" class="text-white" @click="dialogedit = true">
                                            <i class="fa-solid fa-file-pen"></i>
                                        </v-btn>
                                        <!-- dialogEdit END -->
                                        <v-btn color="#D50703" class="text-white">
                                            <i class="fa-solid fa-trash"></i>
                                        </v-btn>
                                    </td>
                                </tr>
                            </tbody>
                        </v-table>
                    </v-card>
                </v-col>
            </v-row>
        </v-main>
        <!-- dialog view -->
        <v-dialog v-model="dialogview" width="auto">
            <v-card>
                <v-toolbar class="text-center text-white" color="#00D1FF" title="VIEW INTO NEWS & ACTIVITIES"></v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-row class="d-flex align-center">
                            <v-col cols="2" class="dialogidunderline">
                                <v-list-subheader>ID : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9" class="dialogtitleunderline">
                                <v-text-field variant="Plain" model-value="2" single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Title : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <v-text-field variant="Plain" model-value="อาคาร" single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Video Name : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <v-text-field variant="Plain" model-value="....." single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Description : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <v-textarea variant="Plain" model-value="......" single-line hide-details
                                    readonly></v-textarea>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>YouTube Link : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <v-text-field variant="Plain" model-value="......" single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Date Create : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <input type="date" name="date">
                            </v-col>
                            <v-col class="d-flex justify-center align-center fileinsert" cols="12" sm="12" md="12">
                                <img :src="app_url + '/images/01.jpg'" alt="">
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card-text>
            </v-card>
        </v-dialog>
        <!-- dialog view END -->
        <!-- dialog edit -->
        <v-dialog v-model="dialogedit" width="auto">
            <v-card>
                <v-toolbar class="text-center text-white" color="#F9A825" title="EDIT INTO NEWS & ACTIVITIES"></v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-row class="d-flex align-center">
                            <v-col cols="2">
                                <v-list-subheader>ID : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="outlined" model-value="2"></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Title : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="outlined" model-value="อาคาร"></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Video Name : </v-list-subheader>
                            </v-col>
                            <v-col cols="9" sm="9" md="9">
                                <v-text-field variant="outlined" model-value="....." single-line hide-details readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Description : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-textarea variant="outlined" value="The Woodman set to work at once,\n and so sharp was his axe that the tree was soon chopped nearly through."></v-textarea>
                                <p v-html="'The Woodman set to work at once,<br> and so sharp was his axe that the tree was soon chopped nearly through.'"></p>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>YouTube Link : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="outlined" model-value="......"></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Date Create : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <input type="date" name="date">
                            </v-col>
                            <v-col class="d-flex justify-center align-center fileinsert" cols="12" sm="12" md="12">
                                <img :src="app_url + '/images/01.jpg'" alt="">
                                <label for="myImage"><i class="mdi mdi-image-plus-outline"></i></label>
                                <input type="file" id="myImage" accept="image/png, image/gif, image/jpeg" />
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card-text>
                <v-card-actions class="d-flex justify-center align-center">
                    <v-btn color="#F9A825" @click="dialogedit = false">
                        <i class="fa-regular fa-xmark"></i>Cancle
                    </v-btn>
                    <v-btn color="#28A745" @click="dialogedit = false">
                        <i class="fa-light fa-floppy-disk"></i>Save
                    </v-btn>

                </v-card-actions>
            </v-card>
        </v-dialog>
        <!-- dialog edit END -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            dialoginsert: false,
            dialogview: false,
            dialogedit: false,
            desserts: [
                {
                    id: 1,
                    title: 'โครงการก่อสร้างอาคารสำนักงานธนาคารออมสินสาขาสุโขทัย',
                    videoname: 'TEAM BUILDING 2020 - LINKINNOVA'
                },
                {
                    id: 2,
                    title: 'WE ARE THE HIGHLY EFFECTIVE TEAM',
                    videoname: ''
                },
                {
                    id: 3,
                    title: 'COTTO FUTSAL CUP ครั้งที่ 3',
                    videoname: ''
                },
                {
                    id: 4,
                    title: 'COTTO FUTSAL CUP ครั้งที่ 2',
                    videoname: ''
                },
                {
                    id: 5,
                    title: 'งานประชุม งานสังสรรค์ ปีใหม่ 2558',
                    videoname: 'TEAM BUILDING 2020 - LINKINNOVA'
                },
                {
                    id: 6,
                    title: 'COTTO FUTSAL CUP ครั้งที่ 1',
                    videoname: ''
                },
                {
                    id: 7,
                    title: 'ปฐมนิเทศพนักงานใหม่ วันที่12 ต.ค55',
                    videoname: 'TEAM BUILDING 2020 - LINKINNOVA'
                },
                {
                    id: 8,
                    title: 'ต้อนรับบริษัท TANGLIN สิงคโปร์ 9-12 สิงหา',
                    videoname: ''
                },
                {
                    id: 9,
                    title: 'งานเลี้ยงขอบคุณทีมงาน ปิดไซต์ โครงสร้างหลัก อาคารเรียนรวม มรภ.กพ',
                    videoname: 'TEAM BUILDING 2020 - LINKINNOVA'
                },

            ],
        }
    },
}
</script>

<style></style>