<script setup lang="ts">
import type { ButtonHTMLAttributes } from 'vue';
import type { Icon } from './icon';

defineProps<{
    /** @default "secondary" */
    variant?: "primary" | "secondary" | "tertiary" | "quaternary";
    /** @default "md" */
    size?: "sm" | "md" | "lg" | "xl";
    icon?: Icon;
    toggled?: boolean;
    title: string;
} & /* @vue-ignore */ ButtonHTMLAttributes>();
</script>

<template>
    <button
    :class="[
            $style.button,
            $style[`button-${size || 'md'}`],
            $style[`button-${variant || 'secondary'}`],
            { [$style.toggled]: toggled },
        ]"
        :title="title"
        :aria-selected="toggled"
    >
    <div v-if="$slots.default" :class="$style.content">
        <slot>
        </slot>
    </div>
    </button>
</template>

<style module></style>