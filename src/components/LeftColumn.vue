<script>
    import { ref } from 'vue';

    const list = ref([1, 2, 3, 4])

    export default {
        methods: {
        handleClick() {
            alert('Icon clicked!');
        },
        MouseOn(index) {
            const icon = document.getElementById("icon" + index); 
            icon.style.backgroundColor = '#FFFFFF';
        },    
        MouseOff(index) {
            const icon1 = document.getElementById("icon" + index);
            icon1.style.backgroundColor = '#F4F1ED';
        },
        },
    };
</script>
 

<template>
    <div id = "app">
        <div class = "icon-container">    
            <img v-for = "(item, index) in list"
            :key = "index"
            :src = "../assets/icon.png">
            :alt = "icon.alt"
            :id = "`icon - ${index + 1}`"
            class = "icon"/>
                
        </div>
            <img id = "icon1" src="../assets/icon.png" alt="Icon" class = "icon1" @click = "handleClick" @mouseover = "MouseOn(1)" @mouseleave = "MouseOff(1)"/>
            <img id = "icon2" src="../assets/icon.png" alt="Icon" class="icon" @click = "handleClick"/>
  </div>
  </template>
  
 
<style>
    .icon-container {
        width: 70px;
        height: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-end;
        background-color:#F4F1ED;
        gap: 20px;
        border-radius: 10px;
        box-sizing: border-box;
    }

    .icon1{
        cursor: pointer;
        width: 50px;
        margin: 60px 0 0 0;
        padding-right: 10px;
    }

    .icon{
        cursor: pointer;
        width: 50px;
        margin-top: 0;
        padding-right: 10px;
    }

</style> 