<template>
  <div>
    <div id="generator-panel" class="generator-panel">
      <label><b>Choose columns count</b></label>
      <br>
      <select v-model="selected">
        <option disabled value="">Columns count</option>
        <option v-for="n in selectOptions">{{ n }} </option>
      </select>
    </div>
    <div class="grid-container-wrapper">
      <b>Grid template will generate here</b>
      <div class="grid-container" v-bind:style="{gridTemplateColumns: [styleText]}">
        <template v-for="item in gridArray">
          <div class="grid-item">{{ item }}</div>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'LeftRightSide',
    data() {
      return {
        selected: '',
        selectOptions: [2,3,4,5,6]
      }
    },
    computed: {
      styleText: function() {
        let returnText = '';
        for(let i = 0; i < this.selected; i++){
          returnText += " auto";
        }
        return returnText;
      },
      gridArray: function() {
        let returnArray = [];
        for(let i = 1; i <= this.selected; i++){
          returnArray.push(i);
        }
        return returnArray;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .generator-panel {
    width: 20%;
    float: left;
  }
  .grid-container-wrapper {
    width: 80%;
    float: left;
  }

  .grid-container {
    display: grid;
    background-color: #2196F3;
    padding: 10px;
    grid-gap: 1em;

  }
  .grid-item {
    background-color: rgba(255, 255, 255, 0.8);
    border: 1px solid rgba(0, 0, 0, 0.8);
    padding: 20px;
    font-size: 30px;
    text-align: center;
  }
</style>
