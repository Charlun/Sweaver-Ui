<template>
  <span ref="Button" id="button" :style="{ backgroundColor: BgColor, color: Color, ...computedStyles, fontSize: FSize, height: Height + 'px', width: Width + 'px',borderRadius: Radius + 'px'}">
    <slot>
    </slot>
  </span>
</template>

<script setup>
// import { onMounted } from "vue"
defineProps({
  Height: {
    type: Number,
  },
  Width: {
    type: Number,
  },
  BgColor: {
    type: String,
  },
  Color: {
    type: String,
    default: 'var(--content-color)'
  },
  FSize: {
    type: String
  },
  Radius: {
    type: Number,
    default: 1000
  }
})
</script>

<style scoped>
#button {
  padding: 5px 2%;
  border: none;
  background-color: var(--primary-color);
  transition: transform 0.1s ease-in-out 0.1ms;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

#button:active {
  transform: scale(0.95) !important;
  filter: brightness(0.8) !important;
}

#button:hover {
  filter: brightness(1.1);
}
</style>
