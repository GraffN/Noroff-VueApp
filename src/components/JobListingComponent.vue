<template>
    <div class="card">
        <div class="row">
            <div class="col-sm-4"></div>
            <div class="col-sm-4"><img :src="thumbnail"> <br> <br> <br> </div>
            <div class="col-sm-4"></div>
        </div>
        <div class="[ card--information ]"> <br />
            <b>Title: </b>{{title}}<br />
            <b>Ingredients: </b><span v-html="ingrediens"></span><br />
            <b>Company Website: </b><a :href="href" target="_blank">Click Here</a><br />
        </div>
    </div>

</template>

<script>
    export default {
        name: 'JobListingComponent',
        props: ['thumbnail','title', 'ingredients','website'],
    }
</script>

<style scoped>
.card{
    border: solid 1px black;
    border-radius: 4px;
    padding: 0px 20px 30px;
    margin-top: 30px;
}
    .card img {
        width: 110px;
        padding-top: 20px;
    }
</style>