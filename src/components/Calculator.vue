<template>
    <div class="calculator">
        <div class="outer_control_panel">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="display_panel">
            <span>{{ currentNumber }}</span>
        </div>
        <div class="main_panel">
            <div class="left_side">
                <button @click="">AC</button>
                <button @click="">+/-</button>
                <button :disabled="true">%</button>
                <button @click="">7</button>
                <button @click="">8</button>
                <button @click="">9</button>
                <button @click="">4</button>
                <button @click="">5</button>
                <button @click="">6</button>
                <button @click="">1</button>
                <button @click="">2</button>
                <button @click="">3</button>
                <button @click="">0</button>
                <button @click="">,</button>
            </div>
            <div class="right_side">
                <button @click="">/</button>
                <button @click="">x</button>
                <button @click="">-</button>
                <button @click="">+</button>
                <button @click="">=</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                currentNumber: 0
            }
        },
        methods: {

        }
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
        height: 400px;
        display: flex;
        justify-content: flex-start;
        flex-wrap: nowrap;
    }
    .main_panel .left_side {
        width: 225px;
        outline: 1px solid white;
        height: 100%;
        display: flex;
        justify-content: flex-start;
        flex-direction: row;
        flex-wrap: wrap;
        align-items:flex-start;
    }
    button {
        width: 75px;
        height: 77.6px;
        font-size: 22px;
    }
    .main_panel .left_side button {
        color: black;
    }
    .main_panel .right_side button {
        background-color: orange;
        color: white;
    }
    .main_panel .right_side {
        width: 75px;
        height: 100%;
    }
</style>