<template>
  <!-- base card -->
  <v-card color="#C0CBEA" width="1240px" height="590px" class="base">
    <!-- main content card -->
    <div class="main-content">
      <div class="title-input">
        <!-- tittle -->
        <div class="title">
          <v-btn text class="add">Tambah Pasien</v-btn>
          <v-btn text>Pendaftaran</v-btn>
          <v-btn text>Cari Pasien</v-btn>
          <v-btn text>Antrian Pasien</v-btn>
          <v-btn text>Checkout Obat</v-btn>
        </div>
        <!-- end tittle -->
        <!-- input card -->
        <v-card color="#fff" width="969px" height="462px" class="card1">
          <!-- <h2>Tambah Pasien Baru</h2> -->
          <v-form>
            <v-container>
              <v-row class="input1">
                <v-col
                  cols="12"
                  sm="6"
                  md="2"
                >
                  <p class="mb-1 ml-1 ">No. Record</p>
                  <v-text-field
                    solo
                    dense
                    v-model="norecord"
                  ></v-text-field>
                </v-col>
                <v-col
                  cols="12"
                  sm="6"
                  md="10"
                >
                  <p class="mb-1 ml-0">Nama Pasien</p>
                  <v-text-field
                    label="Nama"
                    solo
                    dense
                    v-model="namapasien"
                  ></v-text-field>
                </v-col>
              </v-row>

              <div class="mt-n6">
                <p class="mb-1 ml-1">Alamat</p>
                <v-row class="input2">
                  <v-col
                    cols="12"
                    sm="6"
                    md="1"
                  >
                    <v-text-field
                      label="RT"
                      solo
                      dense
                      v-model="rt"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="6"
                    md="1"
                  >
                    <v-text-field
                      label="RW"
                      solo
                      elevation="10"
                      dense
                      v-model="rw"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="4"
                    md="4"
                  >
                    <v-text-field
                      label="Alamat"
                      solo
                      dense
                      v-model="alamat"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="2"
                    md="2"
                  >
                    <v-text-field
                      label="Desa"
                      solo
                      dense
                      v-model="desa"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="2"
                    md="2"
                  >
                    <v-text-field
                      label="Kecamatan"
                      solo
                      dense
                      v-model="kecamatan"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="2"
                    md="2"
                  >
                    <v-text-field
                      label="Kab/Kota"
                      solo
                      dense
                      v-model="kabupatenkota"
                    ></v-text-field>
                  </v-col>
                </v-row>
              </div>
              
              <div class="mt-n5">
                <p class="mb-1 ml-1">Jenis Kelamin</p>
                  <v-radio-group class="mt-n2">
                    <v-row>
                      <v-col
                        cols="12"
                        sm="6"
                        md="2"
                        class="mt-1"
                      >
                          <v-radio
                            label="Laki-laki"
                            value="Laki-laki"
                            v-model="lk"
                          ></v-radio>
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                        md="2"
                        class="mt-1"
                      >
                          <v-radio
                            label="Perempuan"
                            value="Perempuan"
                            v-model="pr"
                          ></v-radio>
                      </v-col>
                    </v-row>
                  </v-radio-group>
              </div>

              <div class="mt-n1">
                <p class="mb-1 ml-1">Nomor Telpon</p>
                <v-row>
                  <v-col
                    cols="12"
                    sm="2"
                    md="4"
                  >
                    <v-text-field
                      label="Nomor Telpon"
                      solo
                      dense
                      v-model="telpon"
                    ></v-text-field>
                  </v-col>
                </v-row>
              </div>

              <div class="mt-n5">
                <p class="mb-1 ml-1">Jenis Pasien</p>
                  <v-radio-group class="mt-n2">
                    <v-row>
                      <v-col
                        cols="12"
                        sm="6"
                        md="2"
                        class="mt-1"
                      >
                          <v-radio
                            label="Umum"
                            value="Umum"
                            v-model="umum"
                          ></v-radio>
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                        md="2"
                        class="mt-1"
                      >
                          <v-radio
                            label="BPJS"
                            value="BPJS"
                            v-model="bpjs"
                          ></v-radio>
                      </v-col>
                      <v-col
                        cols="12"
                        sm="2"
                        md="4"
                        class="ml-n16 mt-n1"
                      >
                        <v-text-field
                          label="Nomor BPJS"
                          solo
                          dense
                          v-model="nomorbpjs"
                        ></v-text-field>
                      </v-col>
                    </v-row>
                  </v-radio-group>
              </div>

              <div class="btn">
                <div>
                  <v-btn @click="save" color="#13C355" width="100px" height="35px" class="simpan-btn white--text heading-2" >
                    <p>SIMPAN</p> 
                  </v-btn>
                </div>
                <div>
                  <v-btn @click="cancel" color="#FF515E" width="100px" height="35px" class="batal-btn white--text heading-2" >
                    <p>BATAL</p> 
                  </v-btn>
                </div>
              </div>
    
            </v-container>
          </v-form>
        </v-card>
        <!-- end input card -->
      </div>
      
      <!-- profile card -->
      <div class="profile">
        
        <!-- biodata card -->
        <v-card color="#fff" width="211px" height="241px" class="card2">
          
        </v-card>
        <!-- end biodata card -->
        
        <!-- action button -->
        <!-- profile button -->
        <div>
          <v-btn color="#13C355" width="211px" height="45px" class="card2 white--text heading-2" >
            <h3>Profile</h3> 
          </v-btn>
        </div>
        <!-- end profile button -->
        <!-- logout button -->
        <div class="button">
          <v-btn color="#FF515E" width="211px" height="45px" class="card2 white--text">
            <h3>Logout</h3>
          </v-btn>
        </div>
        <!-- end logout button -->
      </div>
      <!-- end profile card -->
    </div>
    <!-- end main content card -->
  </v-card>
  <!-- end base card -->

</template>
<script>

export default {

  data(){
    return {
      norecord: "",
      namapasien: "",
      rt: "",
      rw: "",
      alamat: "",
      desa:"",
      kecamatan:"",
      kabupatenkota: "",
      lk:"",
      pr:"",
      telpon: "",
      umum:"",
      bpjs:"",
      nomorbpjs:"",
      data_pasien : [],
      step : 0
    }
    
    
  },
  methods: {
    save() {
      const x = this.norecord.push(this.data_pasien)
      console.log(x)
      // localStorage.namapasien = this.namapasien;
      // localStorage.rt = this.rt;
      // console.log(this.norecord, this.namapasien, this.rt, this.rw, this.alamat, this.desa);
    },
    
    cancel() {
      alert("oke")
    },

    change() {
      if(this.step == 0){
        alert('oke')
      }
    }

  }
};

</script>

<style>
.border {
    border-radius:50px;
}
</style>