<!--
 * @Author: hanjing
 * @Date: 2022-11-10 18:48:16
 * @LastEditTime: 2022-11-14 14:49:41
-->
<template>

   <div class="layout">
        <Menu ></Menu>
    <div class="layout-right">
        <Header></Header>
        <Content>
        </Content>
        <button>给父组件传值</button>
    </div>
   </div>

</template>

<script setup lang='ts'>
import { ref, reactive } from 'vue';
import Menu from "./Menu/index.vue"
import Header from "./Header/index.vue"
import Content from "./Content/index.vue"
// ts 特有 定义默认值 withDefaults
// 给父组件传值使用difineEmits
// withDefaults(defineProps<{title:string,arr:number[]}>(),{arr:() => [4,3]}) 
// const emit = defineEmits(["on-click"])
// const emit = defineEmits<{(e:"on-click",name:string):void}>()
// const send = () => {
// emit("on-click",'hj')
// }
defineExpose({name:'hj',open:()=>console.log(11)})

</script>

 <style scoped lang='less'>
.layout{
    display: flex;
    height: 100%;
    overflow: hidden;
    &-right{
        flex: 1;
        display: flex;
        flex-direction:column;
    }
}
 </style>