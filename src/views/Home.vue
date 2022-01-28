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
                    <a href="../#"><v-btn class="mr-2">Tambah Pasien</v-btn></a>
                    <a href="../findpatien"><v-btn class="mr-2" plain>Daftar</v-btn></a>
                    
                    <v-btn class="mr-2" plain>Cari Pasien</v-btn>
                    <v-btn class="mr-2" plain>Antrian</v-btn>
                    <v-btn plain>Chekout Obat</v-btn>
                  </v-container>
                  <!-- end menu -->
                </v-col> 
              </v-row>  
              <v-row justify="center">
                <!-- content -->
                <v-col cols="9" sm="12" md="9" lg="9" style="padding:0" class="cmargin">
                    <v-card min-width="969px" height="462px" color="white" class="d-none d-sm-flex">
                      <v-form
                      ref="form"
                      @submit.prevent="submit">
                        <v-container>
                          <!-- line 1 -->
                          <v-row style="margin-left:5px; margin-top:-5px">
                            <!-- no record -->
                              <v-col cols="2">
                                <p style="margin-bottom:5px; margin-left:1px">No Record</p>
                                <v-text-field
                                solo
                                dense
                                :rules="rules.requared"
                                v-model="form.norecord"
                                label="No Record"
                                required
                                ></v-text-field>
                              </v-col>
                            <!-- end no record -->

                            <!-- nama pasien -->
                              <v-col cols="10">
                                <p style="margin-bottom:5px; margin-left:1px">Nama Pasien</p>
                                <v-text-field
                                style="max-width:770px"
                                solo
                                dense
                                :rules="rules.requared"
                                v-model="form.nama"
                                label="Nama Pasien"
                                required>
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
                                <v-text-field solo dense :rules="rules.requared" v-model="form.rt" label="RT">
                                </v-text-field>
                              </v-col>
                            <!-- end RT -->

                            <!-- RW -->
                              <v-col cols="1" style="margin-top:-30px">
                                <v-text-field solo dense :rules="rules.requared" v-model="form.rw" label="RW">

                                </v-text-field>
                              </v-col>
                            <!-- end RW -->

                            <!-- Alamat -->
                              <v-col cols="4" style="margin-top:-30px">
                                <v-text-field solo dense :rules="rules.requared" v-model="form.alamat" label="Alamat">

                                </v-text-field>
                              </v-col>
                            <!-- end Alamat -->

                            <!-- Desa -->
                              <v-col cols="2" style="margin-top:-30px">
                                <v-text-field solo dense :rules="rules.requared" v-model="form.desa" label="Desa">

                                </v-text-field>
                              </v-col>
                            <!-- end desa -->

                            <!-- kecamaatan -->
                              <v-col cols="2" style="margin-top:-30px">
                                <v-text-field solo dense :rules="rules.requared" v-model="form.kecamatan" label="Kecamatan">

                                </v-text-field>
                              </v-col>
                            <!-- end kecamatan -->

                            <!-- kabupaten -->
                              <v-col cols="2" style="margin-top:-30px">
                                <v-text-field solo dense :rules="rules.requared" v-model="form.kabkota" label="Kab/Kota">

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
                            <v-radio-group :rules="rules.requared" v-model="form.jk" class="d-inline">
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
                            <v-text-field solo dense :rules="rules.requared" v-model="form.telpon" label="Nomor Telpon">
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
                              <v-radio-group v-model="form.jenispasien" class="d-inline">
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
                                  <v-col cols="8" style="padding:0; margin-left:-10px; margin-top:-7px">
                                    <div class="d-inline">
                                      <v-text-field
                                      solo
                                      dense
                                      label="Nomor BPJS"
                                      style="max-width:250px"
                                      v-model="form.nobpjs"
                                      :disabled="!bpjsIsValid"
                                      :rules="rules.requared"
                                      required
                                      ></v-text-field>
                                    </div>
                                  </v-col>
                                  <!-- end nomor bpjs -->
                                </v-row>                           
                              </v-radio-group>
                            </v-col>
                          <!-- end jenis pasein -->
                        <!-- end line 5 -->
                        
                        <!-- button -->
                        <v-card-actions>
                          <div class="d-flex flex-row-reverse" style="margin-top:-30px">
                          <!-- cancel button -->
                            <v-btn
                            color="#FF515E"
                            style="margin-left:15px"
                            width="100px"
                            @click="resetForm">
                              Batal
                            </v-btn>
                          <!-- end cancel button -->

                          <!-- submit button -->
                          <v-btn color="#13C355" width="100px" type="submit" :disabled="!formIsValid">
                            Simpan
                          </v-btn>
                          <!-- end submit button -->
                          </div>
                        </v-card-actions>
                        <!-- end button -->
                        </v-container>
                      </v-form>

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
    const defaultForm = Object.freeze({
      norecord: null,
      nama : '',
      rt : null,
      rw : null,
      alamat : '',
      desa : '',
      kecamatan : '',
      kabkota : '',
      jk : '',
      telpon : null ,
      nobpjs : '',
      jenispasien : ''
    })
    
    return {
      form: Object.assign({}, defaultForm),
        rules: {
          requared : [
            val => (val || '').length > 0 || 'Wajib di isi'
          ],
          number: value => {
            const pattern = /^[0-9]+$/
            return pattern.test(value) || 'harus angka'
          },
          maks: [
            value => value.length == 2 || 'harus 2 angka'
          ],
          // nobpjs: [val => (val || '').length > 0 || 'Wajib di isi']
        },
        defaultForm,
    }
    
  },

  computed: {
    formIsValid () {
      return (
        this.form.norecord &&
        this.form.nama &&
        this.form.rt &&
        this.form.rw &&
        this.form.alamat &&
        this.form.desa &&
        this.form.kecamatan &&
        this.form.kabkota &&
        this.form.jk &&
        this.form.telpon &&
        this.form.jenispasien 
      )
    },

    bpjsIsValid () {
      return (
        this.form.jenispasien == 'bpjs'
      )
    }
  },

  // watch : {
  //   name () {
  //     this.erroMessage = ''
  //   }
  // },

  methods: {
      resetForm () {
        this.form = Object.assign({}, this.defaultForm)
        this.$refs.form.reset()
      },
      submit () {
        console.log(this.form)
        this.resetForm()
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