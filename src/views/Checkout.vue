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
                    <a href="../#" style="text-decoration:none"><v-btn class="mr-2" plain>Tambah Pasien</v-btn></a>
                    <a href="../addpatien" style="text-decoration:none"><v-btn class="mr-2" plain>Daftar</v-btn></a>
                    <a href="../findpatien" style="text-decoration:none"><v-btn class="mr-2" plain>Cari Pasien</v-btn></a>
                    <a href="../listpatien" style="text-decoration:none"><v-btn class="mr-2" plain>Antrian</v-btn></a>
                    <a href="../checkout" style="text-decoration:none"><v-btn>Chekout Obat</v-btn></a>
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
