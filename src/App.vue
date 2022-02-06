<template>
	<!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <NavBar />
	<Guess 
        :current_word="current_word" 
        :alphabet_check="alphabet_check"
        :guess_check="guess_check"
        :current_guess="current_guess"
        :guesses="guesses"
        />
	<InputBox 
        :current_word="current_word" 
        :inputButton="inputButton"
        :alphabet_check="alphabet_check"
        />
</template>


<script>
	import Guess from "./components/Guess.vue";
	import InputBox from "./components/InputBox.vue";
    import NavBar from "./components/NavBar.vue";

	export default {
		name: "App",
		components: {
			Guess,
			InputBox,
            NavBar
		},

		data() {
			return {
				secret_word: "MOUNT",
				current_word: "",
                alphabet_check: {},
                guess_check: [{'current_word': ''}, {'current_word': ''}, {'current_word': ''}, {'current_word': ''}, {'current_word': ''}],
                current_guess: 0,
                guesses: [0, 1, 2, 3, 4]
			};
		},
		methods: {
			inputButton: function (e) {
                let value = e.target.value
                console.log(value)
                if(e.target.value == "ENTER"){
                    this.checkWord(this.current_word)
                }
                if(e.target.value == "CANCEL" || !e.target.value){
                    console.log('cancel')
                    this.popWord(this.current_word)
                }
                if(value && value != "ENTER" && value != "CANCEL" && this.current_word.length < 5){
                    this.current_word += e.target.value;
                    console.log(this.current_word)
                }
			},
            checkWord: function (word) {
                if(word){
                    let alphabet_check = {}
                    for(let i = 0; i < 5; i++){
                        if(this.current_word[i] == this.secret_word[i]){
                            alphabet_check[this.current_word[i]] = 'green';
                            this.alphabet_check[this.current_word[i]] = 'green';
                        }
                        else if(this.secret_word.includes(this.current_word[i])){
                            alphabet_check[this.current_word[i]] = 'yellow';
                            this.alphabet_check[this.current_word[i]] = 'yellow';
                        }
                        else{
                            alphabet_check[this.current_word[i]] = 'black';
                            this.alphabet_check[this.current_word[i]] = 'black';
                        }
                        // console.log('alphabet check', alphabet_check)
                    }
                    alphabet_check['current_word'] = this.current_word
                    this.guess_check[this.current_guess] = alphabet_check;
                    console.log('this guess now', this.guess_check)
                    // reset values
                    this.current_word = ""
                    this.current_guess++
                }
                console.log('alpha check', this.alphabet_check)
            },
            popWord: function() {
                let string = this.current_word.substring(0, this.current_word.length - 1)
                console.log('string', string)
               this.current_word = string
            }
		},
	};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

*{
    margin: 0;
}
</style>
