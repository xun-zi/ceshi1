<template>
  <div class="suspension">
    <div v-if="curHeight > 800" @click="toTop" title="回到顶部">
      <svg
        data-v-574aa814=""
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class=""
      >
        <path
          data-v-574aa814=""
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M2.75 1C2.33579 1 2 1.33579 2 1.75C2 2.16421 2.33579 2.5 2.75 2.5H13.25C13.6642 2.5 14 2.16421 14 1.75C14 1.33579 13.6642 1 13.25 1H2.75ZM7.24407 3.87287C7.64284 3.41241 8.35716 3.41241 8.75593 3.87287L13.0622 8.84535C13.6231 9.49299 13.163 10.5 12.3063 10.5H10V14C10 14.5523 9.55228 15 9 15H7C6.44772 15 6 14.5523 6 14V10.5H3.69371C2.83696 10.5 2.37691 9.49299 2.93778 8.84535L7.24407 3.87287Z"
          fill="#8A919F"
        ></path>
      </svg>
    </div>
    <div class="feedback" title="反馈意见">
      <svg
        data-v-574aa814=""
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class="icon-feedback"
      >
        <path
          data-v-574aa814=""
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M1.8252 4.002C1.8252 2.80032 2.79935 1.82617 4.00102 1.82617H12.001C13.2027 1.82617 14.1768 2.80032 14.1768 4.002V9.71628C14.1768 10.918 13.2027 11.8921 12.001 11.8921H9.43308L6.92709 14.1281C6.4455 14.5578 5.68234 14.216 5.68234 13.5706V11.8921H4.00102C2.79934 11.8921 1.8252 10.918 1.8252 9.71628V4.002ZM11.2414 7.86753C11.3826 7.65526 11.3249 7.36878 11.1126 7.22764C10.9004 7.08651 10.6139 7.14417 10.4728 7.35643C9.94042 8.15705 9.03153 8.68309 7.99997 8.68309C6.96841 8.68309 6.05952 8.15705 5.52719 7.35643C5.38605 7.14417 5.09957 7.08651 4.88731 7.22764C4.67504 7.36878 4.61738 7.65526 4.75852 7.86753C5.45467 8.91452 6.64645 9.60617 7.99997 9.60617C9.35349 9.60617 10.5453 8.91452 11.2414 7.86753Z"
          fill="#1E80FF"
        ></path>
      </svg>
    </div>
  </div>
</template>

<script setup>
const { onMounted, reactive, watchEffect, ref, onUnmounted }=require("@vue/runtime-core");
const {windowScroll} = require('@/utils/windowScroll') 
let curHeight = ref(0)
let resFun

onMounted(() => {
  resFun =  windowScroll(curHeight)
})

watchEffect(() => {
})
onUnmounted(() => {
  console.log(resFun);
  console.log(111);
  window.removeEventListener('scroll',resFun)
})
const toTop = (e) => {
  window.scrollTo({ top: 0 });
};
</script>

<style lang="scss" scoped>
.suspension {
  width: 40px;
  position: fixed;
  right: 20px;
  bottom: 20px;
  div {
    height: 40px;
    margin: 10px 0;
    text-align: center;
    line-height: 40px;
    cursor: pointer;
    border-radius: 50%;
    background-color: #fff;
  }
}
</style>