<script>


    export default {
        data(){
            return {
                icons: [
                    { src: 'icon.png', alt: 'Icon 1'},
                    { src: 'icon.png', alt: 'Icon 2'},
                    { src: 'icon.png', alt: 'Icon 3'},
                ],
            };
        },
        methods: {
        handleClick() {
            alert('Icon clicked!');
        },
        MouseOn(index) {
            const icon = document.getElementById(`icon${index}`); 
            icon.style.backgroundColor = '#FFFFFF';
        },    
        MouseOff(index) {
            const icon = document.getElementById(`icon${index}`);
            icon.style.backgroundColor = '#F4F1ED';
        },
        },
    };
</script>
 

<template>
    <div id = "app">
        <div class = "icon-container">    
            <img v-for = "(icon, index) in icons"
            :key = "index"
            :src = "icon.src"
            :alt = "icon.alt"
            :id = "`icon${index}`"
            :class = "[index === 0 ? 'icon1' : 'icon']"
            @click = "handleClick()"
            @mouseover = "MouseOn(index)"
            @mouseleave = "MouseOff(index)" />  
        </div>
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