<template>
    <div>
        <v-main>
            <v-row class="ma-1 news-activitie">
                <!-- dialogInsert -->
                <v-dialog v-model="dialoginsert" width="auto">
                    <template v-slot:activator="{ props }">
                        <v-col cols="8" class="d-flex align-end">
                            <v-btn color="#D50703" class="text-white" v-bind="props"><i
                                    class="mdi mdi-text-box-plus-outline"></i>Insert
                            </v-btn>
                        </v-col>
                    </template>
                    <v-card>
                        <v-toolbar class="text-center text-white" color="#D50703"
                            title="INSERT INTO JOIN US"></v-toolbar>
                        <v-card-text>
                            <v-container>
                                <v-row class="d-flex align-center">
                                    <v-col cols="2">
                                        <v-list-subheader>Position : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-text-field variant="outlined" required></v-text-field>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Job Description : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-text-field variant="outlined" required></v-text-field>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Fringe Benefit : </v-list-subheader>
                                    </v-col>
                                    <v-col cols="10" sm="10" md="10">
                                        <v-textarea variant="outlined" required></v-textarea>
                                    </v-col>
                                    <v-col cols="2">
                                        <v-list-subheader>Qualification : </v-list-subheader>
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
                                    <th>Image</th>
                                    <th>Position</th>
                                    <th>Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="item in desserts" :key="item.id">
                                    <td>{{ item.id }}</td>
                                    <td><v-img cover :src="item.image" :height="100" class="ma-1"></v-img></td>
                                    <td>{{ item.position }}</td>
                                    <td>
                                        <!-- dialogView -->
                                        <i class="fa-solid fa-eye ma-2 action-backend-view" @click="dialogview = true"></i>

                                        <!-- dialogView END -->
                                        <!-- dialogEdit -->
                                        <i class="fa-solid fa-file-pen ma-2 action-backend-edit" @click="dialogedit = true"></i>

                                        <!-- dialogEdit END -->
                                        <i class="fa-solid fa-trash ma-2 action-backend-delete"
                                            style="font-size: 20px; color:#D50703; cursor: pointer;"></i>
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
                <v-toolbar class="text-center text-white" color="#00D1FF" title="VIEW JOIN US"></v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-row class="d-flex align-center">
                            <v-col cols="2">
                                <v-list-subheader>Position : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="Plain" model-value="วิศวกรโยธา" single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Job Description : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="Plain" model-value=".........." single-line hide-details
                                    readonly></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Fringe Benefit : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-textarea variant="Plain" model-value=".........." single-line hide-details
                                    readonly></v-textarea>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Qualification : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="Plain" model-value=".........." single-line hide-details
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
                <v-toolbar class="text-center text-white" color="#F9A825" title="EDIT JOIN US"></v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-row class="d-flex align-center">
                            <v-col cols="2">
                                <v-list-subheader>Position : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="วิศวกรโยธา" model-value="วิศวกรโยธา" required></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Job Description : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="outlined" model-value=".........." required></v-text-field>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Fringe Benefit : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-textarea variant="outlined" model-value=".........." required></v-textarea>
                            </v-col>
                            <v-col cols="2">
                                <v-list-subheader>Qualification : </v-list-subheader>
                            </v-col>
                            <v-col cols="10" sm="10" md="10">
                                <v-text-field variant="outlined" model-value=".........." required></v-text-field>
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
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOSrt6-XMPkT24GeFlgLpRT0wBMru6ov33legAXcKIEghudPbTGU5LM-Fwt1Oazw6boIsj1r3p2zQoKe5ykTu2qzt4oNLw=w1325-h650',
                    position: 'วิศวกรโยธา'
                },
                {
                    id: 2,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEORcZDrM9aGMQiinBD7c_oCaib1ALwSeCL-09jF3Ho-HOOpCiOgfxg6-DfWLW5wNoFC7LF49Zp_FSpy7tvzkSzXIVAIM3g=w1325-h650',
                    position: 'วิศวกรไฟฟ้า'
                },
                {
                    id: 3,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOTrXF5Edc6KEThAc6PuuXXdBREMYbpliom25IQh3hBLQeIVQmaf08KWMhiR59zSf8aC0ZVP3V7PxySF4CaTPpNztvFH7g=w1325-h650',
                    position: 'โฟร์แมนไฟฟ้า'
                },
                {
                    id: 4,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOSIOjZR5H6DVaQ3OkRLANLUE1g8yEoatUIFmR1bLulG0RrjIEnQTuxOJY4ShsJTMnmw47nWyUOzsJwEceIKVLPDXE-H3Q=w1325-h650',
                    position: 'โฟร์แมนไฟฟ้า(เดินทางต่างจังหวัด)'
                },
                {
                    id: 5,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOTlcTiIJEr-GCCew7M7XVt54Up31GRxpIZi60PDjTxRPsJNrYMi5fnCr_tnyUhUVxon7xN7uOh5F0mrOuDPL40R3oi-FQ=w1325-h650',
                    position: 'พนักงานขับรถ 6 ล้อ'
                },
                {
                    id: 6,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOSeSLjXKWGBNeCarr317xltQkQC2MTwsL7vY7Tpb6-onLm3DvR163atvEqzaUnnBC9jadkgvLmAJSSTVoM9DEikcyIhyw=w1325-h650',
                    position: 'พนักงานขับรถ 4 ล้อ'
                },
                {
                    id: 7,
                    image: 'https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEORarZy2G2qdB0bDD5UHXirjEICtFgzJfNDEKMW6W4phHBARV9sXBsg1i4imYJr7YmNVRIJkgGNQ7pUsq2X-NLm8rVaQiQ=w1325-h650',
                    position: 'เจ้าหน้าที่ธุรการประจำสำนักงาน'
                },

            ],
        }
    },
}
</script>

<style></style>