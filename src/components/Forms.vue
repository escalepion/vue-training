<template>
  <div>
    <h1>Forms</h1>

    <h3>Checkbox events.V-model</h3>
    <input type="checkbox" id="john" value="Johnn" v-model="checkedItems">
    <label for="john">John</label>
    <input type="checkbox" id="doe" value="Doe" v-model="checkedItems">
    <label for="doe">Doe</label>
    <input type="checkbox" id="akif" value="Akif" v-model="checkedItems">
    <label for="Akif">Akif</label>
    <br>
    <p>{{ checkedItems }}</p>

    <h3>Select Box:</h3>
    <select v-model="selected">
      <option value="">Select one item</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <p>{{ selected }}</p>

  </div>
</template>

<script>
  export default {
    data () {
      return {
        checkedItems: [],
        selected: ''
      }
    }
  }
</script>