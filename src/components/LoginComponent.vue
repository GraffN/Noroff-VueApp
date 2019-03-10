<template>
    <div class="row">
        <div class="col-sm-4"></div>
        <div class="col-sm-4">
            <form>
                <legend>{{message}}</legend>
                <input type="text" placeholder="Username" v-model="username" v-bind:class="{ 'error-border': inputUsernameError}" class="form-control">
                <div class="error" v-if="showUsernameError">Please enter correct Username</div>
                <br>
                <input type="text" placeholder="Password" v-model="password" v-bind:class="{ 'error-border': inputPasswordError}" class="form-control">
                <div class="error" v-if="showUsernameError">Please enter correct Password</div>
                <br>
                <button type="button" v-on:click="login" class="btn btn-default">Submit</button>
            </form>
        </div>
        <div class="col-sm-4"></div>
    </div>
</template>
<script>
    export default {
        name: 'Login',
        props:['message', 'showUsernameError', 'inputUsernameError', 'showPasswordError', 'inputPasswordError'],
        methods:{
            login: function () {
                const app = this;
                app.$emit('clicked', this.username, this.password);
            }

        }
    }
</script>
<style scoped>
    .error{
        color: red;
    }

    .error-border{
        border: solid 1px red;
    }
</style>