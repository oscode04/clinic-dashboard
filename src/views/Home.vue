<template >
  <v-container class="fill-height" fluid>
    <!-- desktop -->
    <v-row>
      <v-col cols="12" sm="12" md="12" class="d-flex justify-center overflow-hidden" >
        <!-- dekstop version -->
        <!-- base card -->
          <v-card height="590px" width="1240px" color="#C0CBEA" class="d-none d-sm-flex">
            <v-container>
              <v-row no-gutters>
                <v-col >
                  <!-- menu -->
                  <v-container class="d-flex justify-start mb-n5 mt-5 ml-n7">
                    <!-- <button v-for="menu in menus" :key="menu.id" :class="{add:menu.kondisi, kosong:menu.kondisi2}" @click="toggle(menu)">{{menu.label}}</button> -->
                    <!-- <button :class="{add:menu.kondisi}" @click="toggle(menu)">Tambah Pasien2</button> -->
                    <!-- <v-btn class="mr-2 add" plain>Tambah Pasien</v-btn>
                    <v-btn class="mr-2">Daftar</v-btn>
                    <v-btn class="mr-2">Cari Pasien</v-btn>
                    <v-btn class="mr-2">Antrian</v-btn>
                    <v-btn >Chekout Obat</v-btn> -->
                  </v-container>
                  <!-- end menu -->
                </v-col> 
              </v-row>  
              <v-row justify="center">
                <!-- content -->
                <v-col cols="9" sm="12" md="9" lg="9" style="padding:0" class="cmargin">
                    <v-card min-width="969px" height="462px" color="white" class="d-none d-sm-flex" ref="form">
                      
                      <!-- line 1 -->
                      <v-container>
                        <v-row style="margin-left:5px; margin-top:-5px">
                          <!-- no record -->
                            <v-col cols="2">
                              <p style="margin-bottom:5px; margin-left:1px">No Record</p>
                              <v-text-field solo dense v-model="norecord" label="No Record">
                              </v-text-field>
                            </v-col>
                          <!-- end no record -->

                          <!-- nama pasien -->
                            <v-col cols="10">
                              <p style="margin-bottom:5px; margin-left:1px">Nama Pasien</p>
                              <v-text-field style="max-width:770px" solo dense v-model="nama" label="Nama Pasien">
                              </v-text-field>
                            </v-col>
                          <!-- end nama pasien -->
                      <!-- end line 1 -->

                      <!-- line 2 -->
                      <v-col cols="12" style="margin-left:1px; margin-top:-37px; margin-bottom:-5px">
                        <p>Alamat</p>
                      </v-col>
                          <!-- RT -->
                            <v-col cols="1" style="margin-top:-30px">
                              <v-text-field solo dense v-model="rt" label="RT">
                              </v-text-field>
                            </v-col>
                          <!-- end RT -->

                          <!-- RW -->
                            <v-col cols="1" style="margin-top:-30px">
                              <v-text-field solo dense v-model="rw" label="RW">

                              </v-text-field>
                            </v-col>
                          <!-- end RW -->

                          <!-- Alamat -->
                            <v-col cols="4" style="margin-top:-30px">
                              <v-text-field solo dense v-model="alamat" label="Alamat">

                              </v-text-field>
                            </v-col>
                          <!-- end Alamat -->

                          <!-- Desa -->
                            <v-col cols="2" style="margin-top:-30px">
                              <v-text-field solo dense v-model="desa" label="Desa">

                              </v-text-field>
                            </v-col>
                          <!-- end desa -->

                          <!-- kecamaatan -->
                            <v-col cols="2" style="margin-top:-30px">
                              <v-text-field solo dense v-model="kecamatan" label="Kecamatan">

                              </v-text-field>
                            </v-col>
                          <!-- end kecamatan -->

                          <!-- kabupaten -->
                            <v-col cols="2" style="margin-top:-30px">
                              <v-text-field solo dense v-model="kabkota" label="Kab/Kota">

                              </v-text-field>
                            </v-col>
                          <!-- end kabupaten -->
                        </v-row>
                      <!-- end line 2 -->
                      
                      <!-- line 3 -->
                      <v-col cols="12" style="margin-left:5px; margin-top:-30px; margin-bottom:-5px">
                        <p>Jenis Kelamin</p>
                      </v-col>

                        <!-- jenis kelamin -->
                        <v-col cols="12" style="margin-left:13px; margin-top:-28px; margin-bottom:-5px">
                          <v-radio-group v-model="jk" class="d-inline">
                            <v-row >
                              <v-col cols="2" style="padding:0">
                                 <div class="d-inline">
                                  <v-radio
                                    label="Laki - laki"
                                    value="laki-laki"
                                    column
                                  ></v-radio>
                                </div>
                              </v-col>

                              <v-col cols="10" style="padding:0; margin-left:-20px">
                                 <div class="d-inline">
                                  <v-radio
                                    label="Perempuan"
                                    value="perempuan"
                                  ></v-radio>
                                </div>
                              </v-col>
                            </v-row>                           
                          </v-radio-group>
                        </v-col>
                        <!-- end jenis kelamin -->
                      <!-- end line 3 -->

                      <!-- line 4 -->
                      <v-row style="margin-left:5px; margin-top:-20px">
                        <v-col cols="5">
                          <p style="margin-bottom:5px; margin-left:1px">Nomor Telpon</p>
                          <v-text-field solo dense v-model="telpon" :rules="[() => !!telpon || 'This field is required']" label="Nomor Telpon">
                          </v-text-field>
                        </v-col>
                      </v-row>
                      <!-- end line 4 -->

                      <!-- line 5 -->
                        <v-col cols="12" style="margin-left:5px; margin-top:-30px; margin-bottom:-5px">
                          <p>Jenis Pasien</p>
                        </v-col>
                        <!-- jenis pasien -->
                          <v-col cols="12" style="margin-left:13px; margin-top:-28px; margin-bottom:-5px">
                            <v-radio-group  class="d-inline">
                              <v-row >
                                <v-col cols="2" style="padding:0">
                                  <div class="d-inline">
                                    <v-radio
                                      label="UMUM"
                                      value="umum"
                                      column
                                    ></v-radio>
                                  </div>
                                </v-col>

                                <v-col cols="2" style="padding:0; margin-left:-20px">
                                  <div class="d-inline">
                                    <v-radio
                                      label="BPJS"
                                      value="bpjs"
                                    ></v-radio>
                                  </div>
                                </v-col>

                                <!-- nomor bpjs -->
                                <v-col cols="8" style="padding:0; margin-left:-60px; margin-top:-7px">
                                  <div class="d-inline">
                                    <v-text-field solo dense label="Nomor BPJS" style="max-width:250px">
                                    </v-text-field>
                                  </div>
                                </v-col>
                                <!-- end nomor bpjs -->
                              </v-row>                           
                            </v-radio-group>
                          </v-col>
                        <!-- end jenis pasein -->
                      <!-- end line 5 -->
                      
                      <!-- button -->
                        <div class="d-flex flex-row-reverse" style="margin-top:-30px">
                        <!-- save button -->
                          <v-btn color="#FF515E" style="margin-left:15px" width="100px" @click="resetForm()">
                            Batal
                          </v-btn>
                        <!-- end save button -->

                        <!-- cancel button -->
                        <v-btn color="#13C355" width="100px" @click="save()">
                          Simpan
                        </v-btn>
                        <!-- end cancel button -->
                        </div>
                      <!-- end button -->
                      </v-container>

                    </v-card>   
                </v-col>
                <!-- end conten -->

                <!-- profile -->
                <v-col cols="3" sm="" md="3" lg="3" style="padding:0 0 0 80px;" class="mr-n5">
                    <v-card max-width="211px" height="241px" color="red" class="d-none d-lg-block "> 

                    </v-card>
                </v-col>
                <!-- end profile -->
              </v-row>
            </v-container>
          </v-card>
        <!-- end base card -->
        <!-- end dekstop version -->

        <!-- mobile version -->
        <!-- base card -->
          <v-card min-height="590px" min-width="500px" color="#C0CBEA" class="d-flex d-sm-none">

          </v-card>
        <!-- end base card -->
        <!-- end mobile version -->
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {

  data(){
    return {
      norecord : null,
      erroMessage : '',
      nama : '',
      rt : null,
      rw : null,
      alamat : '',
      desa : '',
      kecamatan : '',
      kabkota : '',
      jk : '',
      telpon : null,
      formHasErrors : false
    }
    
  },

  computed : {
    form () {
      return {
        noRecord : this.norecord,
        namaPasien : this.nama,
        alamat : [this.rt, this.rw, this.alamat, this.desa, this.kecamatan, this.kabkota],
        jenisKelamin : this.jk,
        telpon : this.telpon
      }
    }
  },

  watch : {
    name () {
      this.erroMessage = ''
    }
  },

  methods :{
      toggle: function(menu) {
        menu.kondisi = !menu.kondisi
      },

      reset () {
          this.norecord = null,
          this.erroMessage = '',
          this.nama = '',
          this.rt = null,
          this.rw = null,
          this.alamat = '',
          this.desa = '',
          this.kecamatan = '',
          this.kabkota = '',
          this.jk = '',
          this.telpon = null,
          this.formHasErrors = false
      },

      resetForm () {
        this.errorMessages = []
        this.formHasErrors = true
        this.reset()
      },

      save () {
        this.formHasErrors = false

        console.log(this.form)
      },
    },
};

</script>

<style>
.add {
  background-color: red;
  color: white;
  border-radius: 7px;
  margin-right: 10px;
  padding: 5px 10px;
}

.kosong {
  color: black;
  margin-right: 10px;
  padding: 5px 10px;
}

.cmargin {
  margin-left: -15px;
  margin-right: 15px;
}
</style>