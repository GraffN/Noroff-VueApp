<template>
    <div class="row">
        <div v-for="job in jobs" class="col-sm-12">
            <JobListingComponent    v-bind:thumbnail="job.thumbnail"
                                    v-bind:title="job.title"
                                    v-bind:ingredients="job.ingredients"
                                    v-bind:website="job.href"
            ></JobListingComponent>
        </div>
    </div>
</template>

<script>

    import JobListingComponent from './components/JobListingComponent.vue'

    export default {
        name: "JobListing",
        components:{
            JobListingComponent
        },
        data(){
            return{
                jobs: []
            }
        },
        beforeMount: function(){
            const app = this;
            if(!sessionStorage.getItem('sessionID')){
                app.$router.push({name: 'Home'});
            }
            const conversionUrl = 'https://cors-anywhere.herokuapp.com/';
            const url = 'http://www.recipepuppy.com/api/';

            fetch(conversionUrl + url)
                .then(function(response){
                    return response.json();
            })
            .then(function(result){
                app.jobs = result;
            })
        }
    }
</script>

<style scoped>

</style>