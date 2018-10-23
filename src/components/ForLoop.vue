<template>
  <div>
    <h1>For Loop</h1>
      <h3>For loop for array</h3>
      <ul>
        <li v-for="(item, index) in arr" v-bind:key="index">
          <a href="#">{{ item.name }}</a>
        </li>
      </ul>

      <h3>For loop in object</h3>
      <ul>
        <li v-for="(value, key, index) in object" :key="index">
          <a href="#">{{ key }} :  {{ value }}</a>
        </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'ForLoop',
  created: function () { console.log(this.arr) },
  data() {
    return {
      arr: [
        {name: 'Akif', age: 93},
        {name: 'Mahmu', age: 57},
        {name: 'Yusuf', age: 56},
        {name: 'Duran', age: 32},
        {name: 'Radi', age:18}
      ],
      object: {
        name: 'Akif',
        age: 32
      }
    }
  }
}
</script>

<style scoped>
  ul {
  list-style-type: none;
  padding: 0;
  }
  li {
  display: inline-block;
  margin: 0 10px;
  }
  a {
  color: #42b983;
  cursor: pointer;
  }
</style>

