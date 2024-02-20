<template>
    <label>
        <input :type="type" :name="Name" :style="{width: Size,height: Size}"/>
        <slot></slot>
    </label>
</template>
<script setup>
import { computed } from 'vue'
const props = defineProps({
    Radio: {
        type: Boolean
    },
    Name: {
        type: String,
        default: ''
    },
    Size: {
        type: String,
        default: '15px'
    }
})
const type = computed(() => {
    return props.Radio ? 'radio' : 'checkbox'
})
</script>
<style scoped>
input {
    appearance: none;
    transition: 0.5s;
    border-radius: 20%;
    box-shadow: 0 0 5px 1px rgba(0, 0, 0, 0.2);
    cursor: pointer;
}
input[type="radio"]{
    border-radius: 50%;
}
input:checked {
    transform: scale(1.3);
    background-color: var(--primary-color);
}
label {
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
}
label::before {
    color: var(--primary-color);
}
</style>
