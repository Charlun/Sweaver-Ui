<template>
    <span :style="{ maxWidth: Width, height: Height, minWidth: Height ,width: Width }" ref="input">
        <svg t="1708398036817" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
            p-id="4243" :width="parentHeight * 0.5" :height="parentHeight * 0.5">
            <path
                d="M799.117225 727.668111A446.399272 446.399272 0 0 0 896.675651 448.449169a51.046313 51.046313 0 1 0-102.165758 0 346.134953 346.134953 0 1 1-39.345152-160.525295 51.046313 51.046313 0 1 0 90.464597-47.462832 448.300711 448.300711 0 1 0-118.035456 558.730412c1.316381 1.828306 2.92529 3.58348 4.534199 5.19239l204.624044 204.624044a51.046313 51.046313 0 0 0 72.181534-72.181534l-204.624044-204.624043a51.558238 51.558238 0 0 0-5.119258-4.5342z"
                fill="#595959" p-id="4244">
            </path>
        </svg>
        <input type="text" :placeholder="Placeholder" :value="Value">
        
    </span>
</template>
<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';
defineProps({
    Width: {
        type: String,
        default: "20%",
    },
    Height: {
        type: String,
        default: "50px",
    },
    Placeholder: {
        type: String,
        default: "Type here...",
    },
    Value: {
        type: String,
    },
})


const parentHeight = ref(0);
const input = ref(null)
const updateParentHeight = () => {
    parentHeight.value = input.value.clientHeight;
};

onMounted(() => {
    parentHeight.value = input.value.clientHeight;
    window.addEventListener('resize', updateParentHeight);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize', updateParentHeight);
});
</script>
<style scoped>
span {
    display: flex;
    padding: 5px;
    border-radius: 100px;
    background: none;
    transition: 0.5s;
    background-color: white;
    box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.2);
    justify-content: center;
    align-items: center;
}

input {
    padding: 0;
    margin: 0 8px;
    outline: none;
    border: 0;
    height: 100%;
    width: 100%;
}

svg {
    transition: 0.5s;
    cursor: pointer;
}

span:focus-within {
    outline: none;
    box-shadow: 0 0 20px 3px rgb(0, 0, 0, 0.1);
    transform: scale(1.02) translate(-3px, -3px);
}
</style>