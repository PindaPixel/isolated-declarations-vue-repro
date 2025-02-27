<script setup lang="ts">
import { ref, useAttrs } from 'vue';

import { Grid as KGrid } from "@progress/kendo-vue-grid";

const gridRef = ref<InstanceType<typeof KGrid>>();

const { test1, test2 } = useAttrs();

</script>

<template>

</template>