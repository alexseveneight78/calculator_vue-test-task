<template>
    <div class="calculator">
        <div class="outer_control_panel">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="display_panel">
            <span>0</span>
        </div>
        <div class="main_panel"></div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    .calculator {
        width: 300px;
        border: 1px solid rgb(0,0,0);
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        flex-wrap: nowrap;
        height: 500px;
    }
    .outer_control_panel {
        display: flex;
        justify-content: flex-start;
        flex-direction: row;
        background-color: rgb(64, 64, 64);
        border: 1px solid black;
        border-radius: 10px;
    }
    .outer_control_panel div {
        width: 15px;
        height: 15px;
        border-radius: 50%;
        cursor: pointer;
        margin: 10px 10px 5px 10px;
    }
    .outer_control_panel :nth-child(1) {
        background-color: red;
    }
    .outer_control_panel :nth-child(2) {
        background-color: yellow;
    }
    .outer_control_panel :nth-child(3) {
        background-color: greenyellow;
    }
    .display_panel {
        background-color: rgb(64,64,64);
        height: 80px;
        color: white;
        display: flex;
        flex-direction: row;
        justify-content: flex-end;
        padding: 10px 20px 10px 0;
        box-sizing: border-box;
        font-size: 60px;
    }
    .main_panel {
        background-color: rgb(230, 230, 230);
    }
</style>