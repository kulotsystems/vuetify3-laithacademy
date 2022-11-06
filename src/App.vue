<template>
    <v-app>
        <!-- SIDEBAR -->
        <side-bar/>
        <v-main>
            <!-- CARDS -->
            <image-gallery/>
        </v-main>
    </v-app>
</template>


<script setup>
    import SideBar from './components/SideBar.vue';
    import ImageGallery from './components/ImageGallery.vue';

</script>


<style scoped>

</style>
