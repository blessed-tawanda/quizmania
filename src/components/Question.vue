<template>
    <div class="question">
        <p> {{number + 1}} {{question.question}} </p>
        <p v-for="(answer,k) in answers" :key="k"> 
            <input type="radio" :name="index" id="" :value="answer" v-model="userAnswer">
            <label for="answer"> {{answer}} </label>
        </p>
    <p v-if="question.showResult"> {{`${question.result};  Correct-Answer: ${question.correct_answer}`}} </p>
    </div>
</template>

<script>
export default {
    created() {
        this.insertCorrectAnswer()
        this.insertIncorrectAnswers()
    },
    data() {
        return {
            userAnswer: "",
            answers: [],
            index: this.number
        }
    },
    props: {
        question: {
            type: Object
        },
        number: {
            type: Number
        }

    },
    methods: {
        insertCorrectAnswer() {
           this.answers[Math.floor(Math.random() * 3)] = this.question.correct_answer
        },
        insertIncorrectAnswers() {
            var counter = 0;
            for( var i = 0; i <= 3; i++) {
                if(this.answers[i]) {
                    continue;
                } else {
                    this.answers[i] = this.question.incorrect_answers[counter];
                    counter++;
                }
            }
        }

    },
    watch: {
        userAnswer: function() {
            if(this.userAnswer == this.question.correct_answer) {
                this.question.correct = true
            } 
        }
    }
   
}
</script>

<style scoped>
    .question {
        padding: 10px;
        border-radius: 3px;
        box-shadow: 0 2px 2px rgba(0,0,0,0.2);
        margin: 10px;
    }
</style>

