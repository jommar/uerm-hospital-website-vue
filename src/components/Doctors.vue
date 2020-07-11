<template>
  <div class="g-font-primary">
    <div class="container">
      <h1 class="h1 mb-3 text-center">Our Doctors</h1>
    </div>
    <div class="g-bg-main py-3">
      <div class="container">
        <div class="my-3">
          <img class="w-100" style="height:280px; object-fit: cover;" src="assets/img/stock/doctors.jpg" alt="doctors" />
        </div>
      </div>
    </div>
    <div class="container">
      <div v-if="doctors.length == 0 && !isDoctorsLoaded" class="p-3 text-center">
        <div>Fetching doctors info</div>
        <div>
          <b class="fa fa-spinner fa-spin"></b>
        </div>
      </div>
      <div class="text-center my-3" v-if="isDoctorsLoaded">
        <span class="btn btn-outline-primary m-2" v-bind:class="{active:curentLetter == ''}" v-on:click="filterDoctors('')">All</span>
        <span
          class="btn btn-outline-primary m-2"
          v-bind:class="{active:curentLetter == letter}"
          v-on:click="filterDoctors(letter)"
          v-bind:key="key"
          v-for="(letter,key) in alphabet"
        >{{letter}}</span>
      </div>
      <div v-if="doctors.length > 0 && isDoctorsLoaded">
        <div v-bind:key="key" v-for="(doctor,key) in doctors">
          <div class="card mb-3 p-3 g-bg-secondary-dark-v2">
            <h3>{{doctor.fullName}}</h3>
            <div class="row mb-3">
              <div class="col-md-3">
                <div class="h4">Area of Specialty</div>
                <div>{{doctor.specialty}}</div>
              </div>
              <div class="col">
                <span class="mx-2">
                  <b>Schedule:</b>
                  {{doctor.sched}}
                </span>
                <span class="mx-2">
                  <b>Room:</b>
                  {{doctor.room}}
                </span>
                <span class="mx-2">
                  <b>Contact No:</b>
                  {{doctor.contactNo}}
                </span>
              </div>
            </div>
            <div class="row" v-if="doctor.hmo != 'N/A' && doctor.hmo != ''">
              <div class="col">
                <div class="h4">HMO Accreditation</div>
                <div
                  v-bind:key="hmoKey"
                  v-for="(hmo,hmoKey) in doctor.hmo.split(',')"
                  class="badge badge-primary mx-1"
                >
                  <span>{{hmo}}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["apiKey"],
  data() {
    return {
      doctors: [],
      isDoctorsLoaded: false,
      alphabet: ["A","B","C","D","E","F","G","H","I","J","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z"],
      curentLetter:'',
    };
  },
  methods: {
    async fetchDoctors() {
      const url = `https://apps.uerm.edu.ph:3443/doctors?auth=${this.apiKey}`;
      const response = await fetch(url, { method: "GET" });
      const responseJson = await response.json();

      this.doctorsAll = responseJson.doctors;
      this.doctors = this.doctorsAll;
      this.isDoctorsLoaded = true;
    },
    filterDoctors(letter) {
      this.curentLetter = letter;
      if (letter == "") {
        this.doctors = this.doctorsAll;
        return;
      }
      this.doctors = this.doctorsAll.filter(doctor => {
        return doctor.fullName.substring(0, 1) == letter;
      });
    }
  },
  mounted() {
    this.fetchDoctors();
    // console.log(this.apiKey);
  }
};
</script>

<style scoped>
</style>