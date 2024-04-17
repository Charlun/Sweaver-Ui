<template>
    <label>
        <slot></slot>
        <input :type="type"
            :style="{ width: Width, height: Height, borderBottom: `${BorderSize} solid ${BorderColor}`, backgroundColor: BgColor }"
            :placeholder="Placeholder" :value="Value">
    </label>
</template>
<script setup>
import { computed } from "vue"

const props = defineProps({
    Passward: {
        type: Boolean,
    },
    Width: {
        type: String,
        default: "200px",
    },
    Height: {
        type: String,
    },
    Placeholder: {
        type: String,
        default: "请输入内容",
    },
    Value: {
        type: String,
        default: "",
    },
    BorderColor: {
        type: String,
        default: "var(--primary-color)",
    },
    BorderSize: {
        type: String,
        default: "5px",
    },
    BgColor: {
        type: String,
        default: "Bgcolor"
    }
})
const type = computed(() => {
    return props.Passward ? "password" : "text"
})
</script>
<style scoped>
input {
    padding: 10px 0;
    margin-bottom: 15px;
    border: 0;
    border-radius: 3px;
    background: none;
    transition: 0.5s;
    font-size: 1.2em;
    font-family: INTREB;
    font-weight: bold;
    color: white;
}
input::placeholder {
    color: white;
}
input:focus {
    outline: none;
    /* box-shadow: 0 0 20px 10px rgb(0, 0, 0, 0.1); */
    transform: scale(1.02) translate(-3px, -3px);
    font-family: INTREB;
    font-weight: bold;
    color: white;
    background: none;
}

label {
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

/* 设置密码输入框右侧按钮的颜色 */
input[type="password"]::-webkit-password-toggle-button {
    -webkit-appearance: none;
    color: white;
}

/* Firefox 特定样式 */
input[type="password"]::-moz-password-eye {
    color: white;
}

/* Edge 特定样式 */
input[type="password"]::-ms-reveal {
    color: white;
}

</style>