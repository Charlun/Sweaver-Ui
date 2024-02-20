<template>
    <span>
        <form action="">
        <input type="text">
        <svg t="1708398036817" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4243" :width="Height*0.5" :height="Height*0.5">
            <path d="M799.117225 727.668111A446.399272 446.399272 0 0 0 896.675651 448.449169a51.046313 51.046313 0 1 0-102.165758 0 346.134953 346.134953 0 1 1-39.345152-160.525295 51.046313 51.046313 0 1 0 90.464597-47.462832 448.300711 448.300711 0 1 0-118.035456 558.730412c1.316381 1.828306 2.92529 3.58348 4.534199 5.19239l204.624044 204.624044a51.046313 51.046313 0 0 0 72.181534-72.181534l-204.624044-204.624043a51.558238 51.558238 0 0 0-5.119258-4.5342z" fill="#595959" p-id="4244">
            </path>
        </svg>
        </form>
    </span>
</template>
<script setup>
defineProps({
    Witdh: {
        type: Number,
        default: 200,
    },
    Height:{
        type: Number,
        default: 50,
    },
    placeholder: {
        type: String,
        default: "请输入内容",
    },
    value: {
        type: String,
        default: "",
    },
})
</script>
<style scoped>
form {
    display: inline-flex;
    align-items: center;
}
span {
    display: inline-block;
    position: relative;

}
input {
    padding: 10px;
    border: 0;
    border-radius: 100px;
    background: none;
    transition: 0.5s;
    background-color: white;
    box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.2);
}
svg {
    position: absolute;
    right: 10px;
    transition: 0.5s;
    cursor: pointer;
}
input:focus + svg {
    transform: scale(1.02) translate(-3px, -3px);
}

input:focus {
    outline: none;
    box-shadow: 0 0 20px 3px rgb(0, 0, 0, 0.1);
    transform: scale(1.02) translate(-3px, -3px);
}

</style>