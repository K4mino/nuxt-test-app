<script lang="ts" setup>
import CustomCheckBox from '~/components/CustomCheckBox.vue';
import Drawer from '~/components/Drawer.vue';
import Accordion from '~/components/Accordion.vue';
import { ref } from 'vue';

const isOpen = ref(false)
const  openDrawer = () => {
    isOpen.value = true
}

</script>

<template>
    <div class="wrapper">
        <h2>Title</h2>
        <p>This is the second page.</p>
        <CustomCheckBox label="Checkbox"/>
        <Drawer>
            <Drawer/>
            <Accordion/>
        </Drawer> 
    </div>
</template>

<style scoped>
    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 20px;
    }
</style>