<script setup>
import {ref,watch} from 'vue'

const count = ref(100)
const changeCount = () => {
    count.value++
}


const name = ref('zhangsan')
const changeName = () => {
    name.value = 'lishi'
}

const userInfo = ref({
    name: 'zs',
    age:18
})
const setUSerInfo = () => {
    userInfo.value.age++
}

//1.监视单个数据
// watch(count,(newValue,oldValue) => {
//     console.log(newValue,oldValue)
// })

//2.监视多个数据
// watch([count,name],(newArr,oldArr) => {
//     console.log(newArr, oldArr)
// },{
//     immediate: true
// })

watch(userInfo,(newValue) =>{
    console.log(newValue)
})

</script>

<template>
    <div>{{ count }}</div>
    <button @click="changeCount">改数字</button>
    <div>{{ name }}</div>
    <button @click="changeName">改名字</button>
    <hr>
    <div>{{ userInfo }}</div>
    <button @click="setUSerInfo">修改用户数据</button>
</template>

<style scoped></style>