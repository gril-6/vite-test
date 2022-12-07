<!--
 * @Author: hanjing
 * @Date: 2022-11-03 11:02:33
 * @LastEditTime: 2022-11-16 11:30:19
-->

<template>

   <layout :title="name" @on-click="getname" ref="water"></layout>
    
</template>
<script setup lang="ts">
import layout from "./layout/index.vue"
import  A  from "./components/A/A.vue";
import { ref, reactive, readonly } from "vue";
import { toRef,toRefs,toRaw } from "vue";
import { Ref } from "vue";
type M = {
    name:String
}
const man:Ref<M>=ref({name:"aa"})
// ref 都支持 取值赋值需要 .value
// reactive 只支持object 不能直接赋值 会破坏响应式对象
// readonly 只读
let form =  reactive<Array<string>>([])
let name = "hj"
const getname = (...name: any[]) => {
    console.log(name);
    
}
const water = ref<InstanceType<typeof layout>>()
water.value?.open

</script>

<style lang = "less">
html,body,#app:nth-child(){
    height: 100%;
    overflow: hidden;
}
</style>
