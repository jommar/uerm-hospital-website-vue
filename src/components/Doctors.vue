<template>
    <div class="container g-font-primary">
        <h1 class="h1 mb-3 text-center">Our Doctors</h1>
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
</template>

<script>
export default {
    props:["doctors"]
}
</script>

<style scoped>

</style>