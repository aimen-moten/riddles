<template>
    <div class="form-main">
      <form @submit.prevent="submitForm">
        <!-- Riddle 1: Checkbox -->
        <p>1. I have keys but open no locks. What am I?</p>
        <input type="checkbox" id="riddle1-opt1" value="piano" v-model="response.riddle1.piano" />
        <label for="riddle1-opt1">Piano</label>
        <input type="checkbox" id="riddle1-opt2" value="door" v-model="response.riddle1.door" />
        <label for="riddle1-opt2">Door</label>
  
        <!-- Riddle 2: Radio -->
        <p>2. What has to be broken before you can use it?</p>
        <input type="radio" id="riddle2-opt1" value="egg" v-model="response.riddle2" />
        <label for="riddle2-opt1">Egg</label>
        <input type="radio" id="riddle2-opt2" value="glass" v-model="response.riddle2" />
        <label for="riddle2-opt2">Glass</label>
  
        <!-- Riddle 3: Dropdown -->
        <p>3. I speak without a mouth and hear without ears. What am I?</p>
        <select v-model="response.riddle3">
          <option disabled value="">Select an answer</option>
          <option value="echo">Echo</option>
          <option value="river">River</option>
        </select>
  
        <!-- Riddle 4: Radio -->
        <p>4. What has words, but never speaks?</p>
        <input type="radio" id="riddle4-opt1" value="book" v-model="response.riddle4" />
        <label for="riddle4-opt1">Book</label>
        <input type="radio" id="riddle4-opt2" value="whisper" v-model="response.riddle4" />
        <label for="riddle4-opt2">Whisper</label>
  
        <!-- Riddle 5: Dropdown -->
        <p>5. The more of this there is, the less you see. What is it?</p>
        <select v-model="response.riddle5">
          <option disabled value="">Select an answer</option>
          <option value="darkness">Darkness</option>
          <option value="light">Light</option>
        </select>
  
        <!-- Buttons -->
        <button type="submit">Submit</button>
        <button type="button" @click="resetQuiz">Reset</button>
      </form>
  
      <div v-if="graded">
        <p>Your Score: {{ score }}/5</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RiddleForm',
    data() {
      return {
        answers: {
          riddle1: "piano",
          riddle2: "egg",
          riddle3: "echo",
          riddle4: "book",
          riddle5: "darkness",
        },
        response: {
          riddle1: { piano: false, door: false },
          riddle2: "",
          riddle3: "",
          riddle4: "",
          riddle5: ""
        },
        score: 0,
        graded: false
      };
    },
    created() {
      this.score = 0;
      this.graded = false;
    },
    methods: {
      submitForm() {
        this.score = 0;
        if (this.response.riddle1.piano && !this.response.riddle1.door) this.score++;
        if (this.response.riddle2 === this.answers.riddle2) this.score++;
        if (this.response.riddle3 === this.answers.riddle3) this.score++;
        if (this.response.riddle4 === this.answers.riddle4) this.score++;
        if (this.response.riddle5 === this.answers.riddle5) this.score++;
        this.graded = true;
      },
      resetQuiz() {
        this.response = { 
          riddle1: { piano: false, door: false }, 
          riddle2: "", 
          riddle3: "", 
          riddle4: "", 
          riddle5: "" 
        };
        this.score = 0;
        this.graded = false;
      }
    }
  };
  </script>
  
  <style scoped>
  h2 {
    color: #333;
  }
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  button {
    margin-top: 10px;
  }
  .form-main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  </style>
  