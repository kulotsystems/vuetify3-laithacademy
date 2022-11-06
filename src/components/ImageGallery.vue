<template>
    <v-row class="pa-5">
        <v-col v-for="n in 200" cols="6" sm="4" md="3" lg="2" xl="1">
            <v-card hover @click="copyURL(`https://picsum.photos/500/300?image=${n * 5 + 10}${params}`)">
                <v-img
                    :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${params}`"
                    :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${params}`"
                    aspect-ratio="1"
                    cover
                >
                    <template v-slot:placeholder>
                        <v-row class="fill-height ma-0" align="center" justify="center">
                            <v-progress-circular indeterminate color="grey-lighten-5"/>
                        </v-row>
                    </template>
                </v-img>
            </v-card>
        </v-col>
    </v-row>
</template>


<script setup>
    import { defineProps, defineEmits, computed } from 'vue';

    const props = defineProps({
        withColor: {
            type    : Boolean,
            required: false,
            default : true
        }
    });

    const emits = defineEmits(['toggleSnackbar']);

    const params = computed(() => {
        return props.withColor ? '' : '&grayscale';
    });

    const copyURL = async (url) => {
        await navigator.clipboard.writeText(url);
        emits('toggleSnackbar', true);
    };
</script>


<style scoped>

</style>
