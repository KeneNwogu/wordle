<template>
    <div class="input-box"> 
        <div class="row width-95">
            <input type="button" maxlength="1" value="Q" @click="inputButton($event)" :class="alphabet_check['Q']">
            <input type="button" class="input" maxlength="1" value="W" @click="inputButton($event)" :class="alphabet_check['W']">
            <input type="button" class="input" maxlength="1" value="E" @click="inputButton($event)" :class="alphabet_check['E']">
            <input type="button" id="" class="input" maxlength="1" value="R" @click="inputButton($event)" :class="alphabet_check['R']">
            <input type="button" id="" class="input" maxlength="1" value="T" @click="inputButton($event)" :class="alphabet_check['T']">
            <input type="button" id="" class="input" maxlength="1" value="Y" @click="inputButton($event)" :class="alphabet_check['Y']">
            <input type="button" id="" class="input" maxlength="1" value="U" @click="inputButton($event)" :class="alphabet_check['U']">
            <input type="button" id="" class="input" maxlength="1" value="I" @click="inputButton($event)" :class="alphabet_check['I']">
            <input type="button" id="" class="input" maxlength="1" value="O" @click="inputButton($event)" :class="alphabet_check['O']">
            <input type="button" id="" class="input" maxlength="1" value="P" @click="inputButton($event)" :class="alphabet_check['P']">
        </div>
        <div class="row width-80">
            <input type="button" id="" class="input" maxlength="1" value="A" @click="inputButton($event)" :class="alphabet_check['A']">
            <input type="button" id="" class="input" maxlength="1" value="S" @click="inputButton($event)" :class="alphabet_check['S']">
            <input type="button" id="" class="input" maxlength="1" value="D" @click="inputButton($event)" :class="alphabet_check['D']">
            <input type="button" id="" class="input" maxlength="1" value="F" @click="inputButton($event)" :class="alphabet_check['F']">
            <input type="button" id="" class="input" maxlength="1" value="G" @click="inputButton($event)" :class="alphabet_check['G']">
            <input type="button" id="" class="input" maxlength="1" value="H" @click="inputButton($event)" :class="alphabet_check['H']">
            <input type="button" id="" class="input" maxlength="1" value="J" @click="inputButton($event)" :class="alphabet_check['J']">
            <input type="button" id="" class="input" maxlength="1" value="K" @click="inputButton($event)" :class="alphabet_check['K']">
            <input type="button" id="" class="input" maxlength="1" value="L" @click="inputButton($event)" :class="alphabet_check['L']">
        </div>
        <div class="row width-95">
            <input type="button" id="" class="input enter" maxlength="1" value="ENTER" @click="inputButton($event)">
            <input type="button" id="" class="input" maxlength="1" value="Z" @click="inputButton($event)" :class="alphabet_check['Z']">
            <input type="button" id="" class="input" maxlength="1" value="X" @click="inputButton($event)" :class="alphabet_check['X']">
            <input type="button" id="" class="input" maxlength="1" value="C" @click="inputButton($event)" :class="alphabet_check['C']">
            <input type="button" id="" class="input" maxlength="1" value="V" @click="inputButton($event)" :class="alphabet_check['V']">
            <input type="button" id="" class="input" maxlength="1" value="B" @click="inputButton($event)" :class="alphabet_check['B']">
            <input type="button" id="" class="input" maxlength="1" value="N" @click="inputButton($event)" :class="alphabet_check['N']">
            <input type="button" id="" class="input" maxlength="1" value="M" @click="inputButton($event)" :class="alphabet_check['M']">
            <button id="" class="input" value="CANCEL" @click="inputButton($event)">
                <img value="CANCEL" id="cancel" src="../assets/icons8-backspace-49.png" alt="" srcset="">               
            </button>
        </div>
    </div>
</template>

<style>
    .input-box{
        position: absolute;
        top: calc(89% - 108px);
        left: calc(50% - 165px);
        margin: 0 auto;
        margin-top: 10px;
    }
    .row{
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
        margin: 0 auto;
        margin-bottom: 12px;
    }

    .width-95{
        width: 95%;
    }

    .width-80{
        width: 85%;
    }
    button{
        background-color: rgb(207, 208, 208);
        border: none;
        border-radius: 7px;
        height: 40px;
    }
    .row > input{
        padding: 10px;
        width: 10%;
        height: 40px;
        text-align: center;
        line-height: 20px;
        border: none;
        background-color: rgb(207, 208, 208);
        border-radius: 7px;
        margin-right: 4px;
    }
    .green, .yellow, .black{
        border: none !important;
    }
    .green{
        background-color: green !important;
        color: white;
    }

    .yellow{
        background-color: yellow !important;
        color: white;
    }

    .black{
        background-color: black !important;
        color: white;
    }
    .enter{
        width: fit-content !important;
        padding: 4px !important;
    }
    #cancel{
        width: fit-content;
    }
</style>

<script>
export default {
    name: "InputBox",
    props: {
        current_word: String,
        inputButton: Function,
        alphabet_check: Object
    },
    watch: {
        alphabet_check: function() {
            
        }
    }
}
</script>