<template>
    <v-navigation-drawer expand-on-hover rail permanent>
        <v-list>
            <v-list-item
                prepend-avatar="https://www.kulotsystems.tech/images/kulotsystems-v1.jpg?d677d330e6cb566ac1565f2b322881ba"
                title="kulotsystems"
                subtitle="kulotsystems@gmailcom"
            />
        </v-list>
        <v-divider/>
        <v-list density="compact" nav>
            <v-list-item
                prepend-icon="mdi-image"
                title="Color Gallery"
                value="color"
                @click="emits('selectOption', true)"
            />
            <v-list-item
                prepend-icon="mdi-dialpad"
                title="Gray Gallery"
                value="gray"
                @click="emits('selectOption', false)"
            />
        </v-list>
    </v-navigation-drawer>
</template>


<script setup>
    import { defineEmits } from 'vue';

    const emits = defineEmits(['selectOption']);
</script>


<style scoped>

</style>
