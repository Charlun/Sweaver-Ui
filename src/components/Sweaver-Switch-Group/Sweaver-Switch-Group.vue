<template>
  <div
    class="SwitchGroup"
    :style="{
      backgroundColor: BgColor,
      height: Height,
      width: Width
    }"
  >
    <!-- 通过v-for渲染-->
    <div
      v-for="(item, index) in buttons"
      :key="index"
      :style="{ width: itemWidth, backgroundColor: ButtonColor }"
      :class="{ button: true, active: index === actionIndex }"
      @click="toggleActionIndex(index)"
      v-html="item.outerHTML"
    >
    </div>
    <div ref="slots" class="box">
      <slot :Height="Height"></slot>
    </div>
    <div
      ref="ActiveElement"
      class="ActiveElement"
      :style="{
        width: itemWidth,
        height: ActiveHeight + 'px',
        borderRadius: ActiveHeight * 0.5 + 'px',
        maxHeight: Height + 'px'
      }"
    >
      <div class="ActiveContent" :style="{ width: ActiveWidth,backgroundColor: ActiveColor,}"></div>
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted, ref} from 'vue'
const buttons = ref([])
onMounted(() => {
  Array.from(slots.value.children).forEach((childElement) => {
    // childElement.setAttribute('Height',props.Height)
    buttons.value.push(childElement)
  })
  console.log(buttons.value[3])
})
let actionIndex = ref(null)
const ActiveElement = ref(null)
const itemWidth = computed(() => 100 / buttons.value.length + '%')
const slots = ref(null)
// const ActivePadding = computed(()=>
//   is(props.ActiveWidth !== undefined){
//   return
// }
// )
// eslint-disable-next-line no-unused-vars
const props = defineProps({
  BgColor: {
    type: String
  },
  Height: {
    type: String,
    default: "20px"
  },
  Width: {
    type: String,
    default: "30%"
  },
  ActiveColor: {
    type: String
  },
  ActiveHeight: {
    type: Number,
    default: 5
  },
  ActiveWidth: {
    type: String,
    default: '100%'
  },
  ButtonColor: {
    type: String,
    default: 'transparent'
  },
  IconMod: {
    type: Boolean,
    default: false
  }
})
const emit = defineEmits(['switchIndex'])
function toggleActionIndex(index) {
  actionIndex.value = index
  ActiveElement.value.style.left = `calc(100%/${buttons.value.length}*${index})`
  console.log(index)
  emit('switchIndex',index)
}
</script>

<style scoped>
.SwitchGroup {
  position: relative;
  display: flex;
  /* background-color: var(--primary-color); */
  align-items: center;
  overflow: hidden;
  border-radius: 100px;
}
.button {
  z-index: 1;
  cursor: pointer;
  display: inline-block;
  list-style: none;
  text-align: center;
}
.ActiveElement {
  z-index: 0;
  position: absolute;
  left: 0;
  bottom: 0;
  height: 100%;
  border-radius: 5px;
  transition: 0.5s;
}
.ActiveContent {
  height: 100%;
  background-color: var(--secondary-color);
  margin: 0 auto;
  border-radius: 25px;
}
.active {
}
.box {
  display: none;
}
.button-content {
  /* 添加按钮内容样式，限制大小等，可根据需要调整 */
  width: 100%;
  overflow: hidden; /* 超出部分隐藏 */
}
.item {
  max-height: 100%;
}
.slots{
  
}
</style>
