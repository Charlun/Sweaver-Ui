<template>
    <div id="avatar-container">
      <div id="avatar" :style="{ height: Size + 'px' ,width: Size + 'px' }">
        <img :src="Src" :alt="Alt" id="img" :style="{ height: Size + 'px' ,width: Size + 'px' }"/>
        <div id="menu" :style="{width: Size + 'px' ,paddingTop: Size + 'px' }">
            <div id="item">
                <slot></slot>
            </div>
        </div>
      </div>
    </div>
</template>
<script setup>
defineProps({
  Size:{
    type: Number,
    default: 30
  },
  Src:{
    type: String,
  },
  Alt:{
    type: String,
    default: 'avatar'
  }
})
</script>
<style>
#avatar-container {
        position: relative;
      }

      #avatar {
        display: block;
        cursor: pointer;
        overflow: hidden;
      }

      #menu {
        z-index: 0;
        position: absolute;
        opacity: 0; 
        background-color: #fff;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        pointer-events: none; /* 初始状态隐藏，不可点击 */
        transition: 0.5s;
        border-radius: 200px;
        overflow: hidden;
        top: 0;

      }
      #avatar:hover #menu {
        opacity: 1;
        pointer-events: auto;
        top: 0;
      }
      /* #avatar:hover {
        opacity: 1;
        display: inline;
        pointer-events: auto;
      } */
      #img {
        position: relative;
        z-index: 999;
        width: 100%;
        border-radius: 100px;
      }
      #item {
        padding: 10px;
      }
      </style>