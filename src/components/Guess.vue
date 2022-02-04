<template>
    <div class="guess" v-for="i in guesses" :key="i">
        <div v-if="i == current_guess">
            <input type="button" v-bind:value="current_word[0]" :class="guess_check[i][current_word[0]]">
            <input type="button" v-bind:value="current_word[1]" :class="guess_check[i][current_word[1]]">
            <input type="button" v-bind:value="current_word[2]" :class="guess_check[i][current_word[2]]">
            <input type="button" v-bind:value="current_word[3]" :class="guess_check[i][current_word[3]]">
            <input type="button" v-bind:value="current_word[4]" :class="guess_check[i][current_word[4]]">
        </div> 
        <div v-else>
            <input type="button" :class="guess_check[i][guess_check[i]['current_word'][0]]" v-bind:value="guess_check[i]['current_word'][0]">
            <input type="button" :class="guess_check[i][guess_check[i]['current_word'][1]]" v-bind:value="guess_check[i]['current_word'][1]">
            <input type="button" :class="guess_check[i][guess_check[i]['current_word'][2]]" v-bind:value="guess_check[i]['current_word'][2]">
            <input type="button" :class="guess_check[i][guess_check[i]['current_word'][3]]" v-bind:value="guess_check[i]['current_word'][3]">
            <input type="button" :class="guess_check[i][guess_check[i]['current_word'][4]]" v-bind:value="guess_check[i]['current_word'][4]">
        </div>
    </div>

    <!-- <div class="guess">
        <input type="button" v-bind:value="current_word[0]" :class="guess_check[current_word[0]]">
        <input type="button" v-bind:value="current_word[1]" :class="guess_check[current_word[1]]">
        <input type="button" v-bind:value="current_word[2]" :class="guess_check[current_word[2]]">
        <input type="button" v-bind:value="current_word[3]" :class="guess_check[current_word[3]]">
        <input type="button" v-bind:value="current_word[4]" :class="guess_check[current_word[4]]">
    </div> -->
</template>

<script>
export default {
    name: "Guess",
    props: {
        current_word: String,
        alphabet_check: Object,
        guess_check: Array,
        guesses: Array,
        current_guess: Number
        // active: Boolean
    }
}
</script>

<style>
    .guess{
        display: flex;
        flex-direction: row;
        align-items: center;
        margin: 0 auto;
        justify-content: space-around;
        width: 60%;
        margin-bottom: 12px;
    }
    .guess > div {
        display: inline;
    }
    .guess > div > input{
        width: 12%;
        height: 30px;
        text-align: center;
        background-color: white;
        border: 1px solid grey;
        padding: 12px;
        line-height: 15px;
        margin-right: 10px;
        /* border: none; */
        /* margin-right: -20%; */
    }
</style>