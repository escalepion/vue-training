<template>
  <div class="hello">
    <h1>{{ msg }} {{ akif }}</h1>
    <p><button @click="clicking()">button</button></p>
    <p v-bind:title="akif">Hover over me and look at title</p>
    <h1>Change seen status</h1>
    <p><button v-on:click="hanleChangeClick">Change status</button></p>
    <transition name="fade">
      <p v-if="seen">Now you see me</p>
    </transition>
    <h1>Input events</h1>
    <p>{{ inputData }}</p>
    <input v-model="inputData" >
    <ForLoop />
    <TemplateSyntax />
    <ComputedProperties />
    <WatchProperties />
    <ClassAndStyle />
    <IfThenElse />
    <Todo />
    <Forms />
  </div>
</template>

<script>
import ForLoop from './ForLoop.vue';
import TemplateSyntax from './TemplateSyntax';
import ComputedProperties from './ComputedProperties';
import WatchProperties from './WatchProperties';
import ClassAndStyle from './ClassAndStyle';
import IfThenElse from './IfThenElse';
import Todo from './Todo';
import Forms from './Forms';

export default {
  name: 'HelloWorld',
  components: {
    ForLoop,
    TemplateSyntax,
    ComputedProperties,
    WatchProperties,
    ClassAndStyle,
    IfThenElse,
    Todo,
    Forms
  },
  props: {
    msg: String
  },
  methods: {
  clicking () {
    this.akif = 'degisti'
  },
  hanleChangeClick () {
    this.seen = !this.seen;
  }
  },
  data() {
    return {
      akif: 'deneme',
      seen: true,
      inputData: 'input default data'
    };
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
