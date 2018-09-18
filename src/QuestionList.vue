<template>
    <div class="question-list">
        <h1 style="text-align: center" > Welcome To Quiz Mania </h1>
        <question v-for="(question,k) in questions" :question="question" :key="k" :number="k" ></question>
        
        <div class="evaluate">
            <button @click="evaluateAnswers" >Evaluate Results </button>
        </div>
    </div>
    
</template>

<script>
import question from './components/Question.vue'
export default {
    data: function () {
        return {
            questions:[
        {
            "question": "By what name is Carlos Estevez better known? ",
            "correct_answer": "Charlie Sheen",
            "incorrect_answers": [
                "Ricky Martin",
                "Bruno Mars",
                "Joaquin Phoenix"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "Which actress married Michael Douglas in 2000?",
            "correct_answer": "Catherine Zeta-Jones",
            "incorrect_answers": [
                "Ruth Jones",
                "Pam Ferris",
                "Sara Sugarman"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "What does film maker Dan Bell typically focus his films on?",
            "correct_answer": "Abandoned Buildings and Dead Malls",
            "incorrect_answers": [
                "Historic Landmarks",
                "Action Films",
                "Documentaries "
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "What was the cause of Marilyn Monroes suicide?",
            "correct_answer": "Drug Overdose",
            "incorrect_answers": [
                "Knife Attack",
                "House Fire",
                "Gunshot"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "Gwyneth Paltrow has a daughter named...?",
            "correct_answer": "Apple",
            "incorrect_answers": [
                "Lily",
                "French",
                "Dakota"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "Which celebrity announced his presidency in 2015?",
            "correct_answer": "Kanye West",
            "incorrect_answers": [
                "Donald Trump",
                "Leonardo DiCaprio",
                "Miley Cyrus"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "Aubrey Graham is better known as",
            "correct_answer": "Drake",
            "incorrect_answers": [
                "Travis Scott",
                "Lil Wayne",
                "2 Chainz"
            ],
            "correct": false,
            "showResult": false
        },
        {
            "question": "By which name is Ramon Estevez better known as?",
            "correct_answer": "Martin Sheen",
            "incorrect_answers": [
                "Charlie Sheen",
                "Ramon Sheen",
                "Emilio Estevez"
            ],
            "correct": false,
            "showResult": false,
            "result": ""
        }
    ]
        }
    },
    components: {
        question: question
    },
    methods: {
        evaluateAnswers() {
            
            this.questions.forEach( (question)=> {
                question.showResult = true;
                if (question.correct) {
                    question.result = "Correct"
                } else {
                    question.result = "Incorrect"
                }
            })
        }
    }
}
</script>

<style scoped>
    .question-list {
        margin: 0 auto;
        padding: 0 60px;
    }
    .evaluate {
        text-align: center;
        padding: 10px;
        margin: 4px;
    }
    h1 {
        text-transform: capitalize;
        text-decoration: underline;
    }

    button{
        border: none;
        border-width: 1px;
        border-style: solid;
        border-color: #4DD0E1;
        border-radius: 3px;
        padding: 10px;
        width: 30%;
        text-transform: uppercase;
        text-decoration: none;
        background-color: #4DD0E1;
    }

    button:hover {
        cursor: pointer;
        transform: translateY(-3px);
        box-shadow: 0 1px 2px rgba(0,0,0,0.2)
    }

    button:active{
        outline: none;
        transform: translateY(-1px);
        box-shadow: 0 0.5px 1px rgba(0,0,0,0.2)
    }
    
    button:focus {
         outline: none;
    }

    

</style>
