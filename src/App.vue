<template>
    <v-app>
        <!-- SIDEBAR -->
        <side-bar @selectOption="onSelectOption"/>
        <v-main>
            <!-- CARDS -->
            <image-gallery :withColor="isWithColor" @toggleSnackbar="toggleSnackbar"/>

            <!-- SNACKBAR -->
            <snackbar :open="isSnackbarOpen" @toggle="toggleSnackbar"/>
        </v-main>
    </v-app>
</template>


<script setup>
    import SideBar      from './components/SideBar.vue';
    import ImageGallery from './components/ImageGallery.vue';
    import Snackbar     from './components/Snackbar.vue';
    import { ref } from 'vue';


    const isWithColor    = ref(true);
    const isSnackbarOpen = ref(false);


    const onSelectOption = (isColor) => {
        isWithColor.value = isColor;
    };

    const toggleSnackbar = (bool) => {
        isSnackbarOpen.value = bool;
    };
</script>


<style scoped>

</style>
