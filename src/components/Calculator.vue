<template>
    <div class="calculator">
        <div class="outer_control_panel">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="display_panel">
            <span>{{ currentExpression }}</span>
        </div>
        <div class="main_panel">
            <div class="left_side">
                <button @click="allClear" ref="AC">AC</button>
                <button @click="addPlusMinus" ref="plusMinus">{{ plusMinus }}</button>
                <button :disabled="true">%</button>
                <button @click="addSeven" ref="seven">{{ seven }}</button>
                <button @click="addEight" ref="eight">{{ eight }}</button>
                <button @click="addNine" ref="nine">{{ nine }}</button>
                <button @click="addFour" ref="four">{{ four }}</button>
                <button @click="addFive" ref="five">{{ five }}</button>
                <button @click="addSix" ref="six">{{ six }}</button>
                <button @click="addOne" ref="one">{{ one }}</button>
                <button @click="addTwo" ref="two">{{ two }}</button>
                <button @click="addThree" ref="three">{{ three }}</button>
                <button @click="addZero" ref="zero">{{ zero }}</button>
                <button @click="addComma" ref="comma">{{ comma }}</button>
            </div>
            <div class="right_side">
                <button @click="addDivide" ref="divide">/</button>
                <button @click="addMultiply" ref="multiply">x</button>
                <button @click="addMinus" ref="minus">-</button>
                <button @click="addPlus" ref="plus">+</button>
                <button @click="addEqual" ref="equal">=</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                plusMinus: '+/-',
                one: '1',
                two: '2',
                three: '3',
                four: '4',
                five: '5',
                six: '6',
                seven: '7',
                eight: '8',
                nine: '9',
                zero: '0',
                comma: ',',
                minus: '-',
                plus: '+',
                divide: '/',
                multiply: '*',
                currentExpression: '0',
                arr: []
            }
        },
        methods: {
            addOne(){
                this.removeInitialZero();
                this.arr.push(this.one);
                this.currentExpression += this.one;
            },
            addTwo(){
                this.removeInitialZero();
                this.arr.push(this.two);
                this.currentExpression += this.two;
            },
            addThree(){
                this.removeInitialZero();
                this.arr.push(this.three);
                this.currentExpression += this.three;
            },
            addFour(){
                this.removeInitialZero();
                this.arr.push(this.four);
                this.currentExpression += this.four;            
            },
            addFive(){
                this.removeInitialZero();
                this.arr.push(this.five);
                this.currentExpression += this.five;
            },
            addSix(){
                this.removeInitialZero();
                this.arr.push(this.six);
                this.currentExpression += this.six;
            },
            addSeven(){
                this.removeInitialZero();
                this.arr.push(this.seven);
                this.currentExpression += this.seven;
            },
            addEight(){
                this.removeInitialZero();
                this.arr.push(this.eight);
                this.currentExpression += this.eight;
            },
            addNine(){
                this.removeInitialZero();
                this.arr.push(this.nine);
                this.currentExpression += this.nine;
            },
            addZero(){
                this.removeInitialZero();
                this.arr.push(this.zero);
                this.currentExpression += this.zero;
            },
            addComma(){
                this.arr.push(this.comma);
                this.currentExpression += this.comma;
            },
            addDivide(){
                this.arr.push(this.divide);
                this.currentExpression += this.divide;
            },
            addMultiply(){
                this.arr.push(this.multiply);
                this.currentExpression += this.multiply;
                console.log(this.arr)
            },
            addPlus(){
                this.arr.push(this.plus);
                this.currentExpression += this.plus;
            },
            addMinus(){
                this.arr.push(this.minus);
                this.currentExpression += this.minus;
            },
            addEqual(){
                let calculation = this.arr.join('');
                this.currentExpression = eval(calculation);
                console.log(typeof this.arr);
                this.arr.length = 0;
                this.arr.push(this.currentExpression.toString());
                console.log(typeof this.arr);
            },
            removeInitialZero(){
                if(this.arr[0] === '0' && this.arr.length === 1) {
                    this.arr.shift();
                    this.currentExpression = '';
                }
            },
            allClear(){
                this.arr.length = 0;
                this.currentExpression = '0';
                this.arr.push(this.currentExpression);
            },
            addPlusMinus(){
                console.log('+/-');
            }
        },
        created(){
            this.arr.push(this.currentExpression);
        }
    }
</script>

<style scoped>
    .calculator {
        width: 360px;
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
        padding: 10px 5px 10px 0;
        box-sizing: border-box;
        font-size: 55px;
    }
    .main_panel {
        background-color: rgb(230, 230, 230);
        height: 400px;
        display: flex;
        justify-content: flex-start;
        flex-wrap: nowrap;
    }
    .main_panel .left_side {
        width: 270px;
        outline: 1px solid white;
        height: 100%;
        display: flex;
        justify-content: flex-start;
        flex-direction: row;
        flex-wrap: wrap;
        align-items:flex-start;
    }
    button {
        width: 90px;
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
        width: 80px;
        height: 100%;
    }
</style>