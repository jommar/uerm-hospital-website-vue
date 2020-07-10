<template>
    <div class="container g-font-primary">
        <h1 class="h1 mb-3 text-center">Our Doctors</h1>
        <div v-if="doctors.length == 0 && !isDoctorsLoaded" class="p-3 text-center">
            <div>Fetching doctors info</div>
            <div><b class="fa fa-spinner fa-spin"></b></div>
        </div>
        <div class="text-center" v-if="isDoctorsLoaded">
            <span class="btn btn-outline-primary m-2" v-on:click="filterDoctors('')">All</span>
            <span class="btn btn-outline-primary m-2" v-on:click="filterDoctors(letter)" v-bind:key="key" v-for="(letter,key) in alphabet">{{letter}}</span>
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
                            <span class="mx-2"><b>Schedule:</b> {{doctor.sched}}</span>
                            <span class="mx-2"><b>Room:</b> {{doctor.room}}</span>
                            <span class="mx-2"><b>Contact No:</b> {{doctor.contactNo}}</span>
                        </div>
                    </div>
                    <div class="row" v-if="doctor.hmo != 'N/A' && doctor.hmo != ''">
                        <div class="col">
                            <div class="h4">HMO Accreditation</div>
                            <div v-bind:key="hmoKey" v-for="(hmo,hmoKey) in doctor.hmo.split(',')" class="badge badge-primary mx-1">
                                <span>{{hmo}}</span>
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
    props:["doctors","filterDoctors","alphabet","isDoctorsLoaded"]
}
</script>

<style scoped>

</style>