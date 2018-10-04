<template>
    <div>
        <app-header></app-header>
        <main role="main">
            <router-view></router-view>
            <app-footer></app-footer>
        </main>
    </div>
</template>

<script>
//import Vue from "vue";
import { mapState, mapActions } from 'vuex'
import AppHeader from "../components/core/AppHeader";
import AppFooter from "../components/core/AppFooter";

export default {
    name: 'app',
    components: {
        AppHeader,
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

<style lang="scss">
    @import '../scss/custom-bootstrap.scss';
    @import '../../node_modules/bootstrap/scss/bootstrap.scss';
</style>