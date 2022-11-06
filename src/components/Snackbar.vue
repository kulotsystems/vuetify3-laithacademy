<template>
    <v-snackbar
        :timeout="3000"
        color="blue-grey"
        rounded="pill"
        v-model="isOpen"
    >
        Image URL Copied to clipboard.

        <template v-slot:actions>
            <v-btn
                variant="text"
                rounded
                @click="emits('toggle', false)"
            >
                Close
            </v-btn>
        </template>
    </v-snackbar>
</template>


<script setup>
import { defineProps, defineEmits, computed } from 'vue';

    const props = defineProps({
        open: {
            type    : Boolean,
            required: false,
            default : false
        }
    });

    const isOpen = computed({
        get() {
            return props.open;
        },
        set() {
            emits('toggle', false);
        }
    });

    const emits = defineEmits(['toggle']);
</script>


<style scoped>

</style>
