<template>
  <div>
    <h1>Watch properties</h1>
    <h3>This example watching input and fetch data</h3>
    <p>{{question}}</p>
    <input v-model="question"/>
    <p>Answer : {{ answer }}</p>
  </div>
</template>

<script>
  import axios from 'axios';
  import _ from 'lodash';

  export default {
    data() {
      return {
        question: '',
        answer: 'type something'
      }      
    },

    created: function (){
      this.debouncedGetAnswer = _.debounce(this.getAnswer, 500)
    },

    watch: {
      question: function () {
        this.answer = 'Waiting for you stop typing...';
        this.debouncedGetAnswer();
      }
    },

    methods: {
      getAnswer: function () {
        var questArr = this.question.split('');
        var lastChar = questArr[questArr.length-1];
        if(lastChar !== '?') {
          this.answer = 'Please put a question mark to end of sentence';
          return ;
        }

        this.answer = 'Thinking';
        var vm = this;
        axios.get('https://yesno.wtf/api')
        .then( function (response) { 
          vm.answer = response.data.answer;
        })
        .catch(function (error)  {
          vm.answer = 'An error occured' + error;
        })
      }
    }
  }
</script>
