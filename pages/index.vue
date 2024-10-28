<template>
    <v-container style="margin: 0; padding: 0">
        <div style="min-height: 0px"/>
        <div class="section" id="home">
            <home/>
        </div>
        <div class="section" id="services">
            <services/>
        </div>
        <div class="section" id="benefits">
            <benefits/>
        </div>
        <div class="section" id="about-us">
            <aboutUs/>
        </div>
        <div class="section" id="clients">
            <clients/>
        </div>
        <div class="section" id="contact-us">
            <contactUs/>
        </div>
    </v-container>
</template>
<script>
import home from '@/layouts/pages/home.vue';
import aboutUs from '@/layouts/pages/about-us.vue';
import services from '@/layouts/pages/services.vue';
import clients from '@/layouts/pages/clients.vue';
import contactUs from '@/layouts/pages/contact-us.vue';
import benefits from '@/layouts/pages/benefits.vue';
import Clients from '../layouts/pages/clients.vue';

export default{
    components:{
        aboutUs,
        services,
        home,
        benefits,
        clients,
        contactUs
    },
}
</script>
<style>
.section{
    width: 100vw;
    min-height: 50vh;
    position: relative;
    box-sizing: border-box;
}
#home{
    background-image: transparent;
    min-height: 100vh;
}
#services{
    background-color: white;
}
#about-us{
    background-color: white;
}
#contact-us{
    background-color: white;
}
</style>