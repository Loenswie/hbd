<template>
  <div class="quiz">
    <h1 style="text-align: center;">Verjaardagsquiz</h1>

    <div v-if="currentQuestionIndex < questions.length">
      <h3>{{ currentQuestionIndex + 1 }}. {{ currentQuestion.text }}</h3>
      <div v-for="(option, i) in currentQuestion.options" :key="i" class="option">
        <label>
          <input
            type="radio"
            :name="'question' + currentQuestionIndex"
            :value="option"
            v-model="selectedAnswer"
          />
          {{ option }}
        </label>
      </div>

      <button @click="submitAnswer">Antwoord indienen</button>

      <p v-if="showFeedback" :class="{ correct: isAnswerCorrect, incorrect: !isAnswerCorrect }">
        {{ feedbackMessage }}
      </p>
    </div>

    <div v-else>
      <h2>Je hebt de quiz voltooid!</h2>
      <p>Je hebt {{ score }} van de {{ questions.length }} vragen goed beantwoord!</p>
      <button @click="resetQuiz">Opnieuw proberen</button>
      <button @click="$router.push('/filmpje')">Toon een speciaal filmpje</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentQuestionIndex: 0,
      selectedAnswer: null,
      showFeedback: false,
      isAnswerCorrect: false,
      feedbackMessage: '',
      score: 0,
      questions: [
        {
          text: 'Wanneer is jouw verjaardag?',
          options: ['Vandaag!', 'Gisteren', 'Morgen', 'Ik vergeet het elk jaar...'],
          correctAnswer: 'Vandaag!',
          answerSentence: 'Goedzo! Je weet wanneer je jarig bent!'
        },
        {
          text: 'Welke nationale dag valt er op jouw verjaardag?',
          options: ['Nationale Pannenkoekendag', 'Nationale Knuffeldag', 'Nationale Oerang Oetang Dag', 'Nationale Pyjamadag'],
          correctAnswer: 'Nationale Oerang Oetang Dag',
          answerSentence: 'Goedzo! Monkey business is jouw business.'
        },
        {
          text: 'Welke hoort niet in het rijtje thuis?',
          options: ['Taart', 'Cadeautjes', 'Slingers', 'Kerstboom'],
          correctAnswer: 'Kerstboom',
          answerSentence: 'Tenzij je ik bent, dan hoort de kerstboom er wel bij. :('
        },
        {
          text: 'Wanneer is de verjaardag van Evan Peters?',
          options: ['20 januari', '20 februari', '20 maart', '20 april'],
          correctAnswer: '20 januari',
          answerSentence: 'Evan Peters is jarig op 20 januari! Als je dit niet juist had, dan is het tijd om jezelf te schamen.'
        },
        {
          text: 'Hoe oud kan een Capibara worden?',
          options: ['6 jaar', '8 jaar', '12 jaar', '20 jaar'],
          correctAnswer: '12 jaar',
          answerSentence: 'Een Capibara kan wel 12 jaar oud worden! Jij flext dus op de leeftijd van een Capibara met 9 jaar sinds vandaag!'
        },
        {
          text: 'Wat heb je niet nodig om een taart te bakken in Minecraft?',
          options: ['Suiker', 'Ei', 'Tarwe', 'Appel'],
          correctAnswer: 'Appel',
          answerSentence: 'Je hebt geen appel nodig om een taart te bakken in Minecraft! Maar je hebt wel een appel nodig om de dokter weg te houden.'
        },
        {
          text: 'Ben jij nog steeds jong?',
          options: ['Ja', 'Nee', 'Misschien', 'Ik ben een dood'],
          correctAnswer: 'Ja',
          answerSentence: 'Volgens de Amerikaanse wet mag je eigenlijk nog maar net een kriekje drinken. Dus ja, je bent nog steeds jong. :)'
        },
      ]
    };
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentQuestionIndex];
    }
  },
  methods: {
    submitAnswer() {
      if (this.selectedAnswer) {
        this.showFeedback = true;
        this.isAnswerCorrect = this.selectedAnswer === this.currentQuestion.correctAnswer;
        this.feedbackMessage = this.isAnswerCorrect
          ? this.currentQuestion.answerSentence
          : `EUUUUH FOUT JONGEDAME`;
        
        if (this.isAnswerCorrect) {
          this.score++;
          setTimeout(() => {
          this.showFeedback = false;
          this.selectedAnswer = null;
          this.currentQuestionIndex++;
          }, 3000); // Wait 3 seconds before moving to the next question
        }

        
      } else {
        alert("Selecteer een antwoord voordat je verder gaat!");
      }
    },
    resetQuiz() {
      this.currentQuestionIndex = 0;
      this.selectedAnswer = null;
      this.showFeedback = false;
      this.isAnswerCorrect = false;
      this.feedbackMessage = '';
      this.score = 0;
    }
  }
};
</script>

<style scoped>
.quiz {
  font-family: Arial, sans-serif;
  text-align: left;
  padding: 20px;
}

.option {
  margin: 5px 0;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

.correct {
  color: green;
}

.incorrect {
  color: red;
}

h1 {
  margin-bottom: 2rem;
}
</style>
