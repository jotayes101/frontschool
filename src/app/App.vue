<template>
    <div class="jumbotron">
        <AppHeader></AppHeader>
        <AppMenu></AppMenu>
        <div class="container">
            <div class="row">
                <div class="col-sm-6 offset-sm-3">
                    <div v-if="alert.message" :class="`alert ${alert.type}`">{{alert.message}}</div>
                    <router-view></router-view>
                </div>
            </div>
        </div>
        <AppFooter></AppFooter>
    </div>
</template>

<script>
//import Vue from "vue";
import { mapState, mapActions } from 'vuex'
import AppHeader from "../components/core/header/index";
import AppMenu from "../components/core/menu/index";
import AppFooter from "../components/core/footer/index";

export default {
    name: 'app',
    components: {
        AppHeader,
        AppMenu,
        AppFooter
    },
    computed: {
        ...mapState({
            alert: state => state.alert
        })
    },
    methods: {
        ...mapActions({
            clearAlert: 'alert/clear' 
        })
    },
    watch: {
        $route (to, from){
            // clear alert on location change
            this.clearAlert();
        }
    } 
};
</script>