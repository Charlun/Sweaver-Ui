<template>
    <label>
        <slot></slot>
        <input :type="type" :style="{ width: Witdh + 'px' ,height : Height + 'px' }" :placeholder="Placeholder" :value="Value">
    </label>
</template>
<script setup>
import { computed } from "vue"

const props = defineProps({
    Passward: {
        type: Boolean,
    },
    Witdh: {
        type: Number,
        default: 200,
    },
    Height:{
        type: Number,
    },
    Placeholder: {
        type: String,
        default: "请输入内容",
    },
    Value: {
        type: String,
        default: "",
    },
})
const type = computed(() => {
    return props.passward ? "password" : "text"
})
</script>
<style scoped>
input {
    padding: 10px 0;
    margin-bottom: 15px;
    border: 0;
    border-radius: 3px;
    border-bottom: 5px solid var(--primary-color);
    background: none;
    transition: 0.5s;
    background-color: var(--background-color);
}

input:focus {
    outline: none;
    box-shadow: 0 0 20px 10px rgb(0, 0, 0, 0.1);
    transform: scale(1.02) translate(-3px, -3px);
}

label {
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}
</style>