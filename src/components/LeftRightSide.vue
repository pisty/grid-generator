<template>
  <div class="layout">
    <div class="generator-panel">
      <h3>
        Choose columns count
      </h3>
      <select class="generator-select" v-model="selected">
        <option v-for="n in selectOptions" :value="n">{{ n }}</option>
      </select>
    </div>
    <div class="grid-container-wrapper">
      <h3>
        Grid template will generate here
      </h3>
      <div class="grid-container">
        <div v-for="item in grids" class="grid-item">{{ item + 1 }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'LeftRightSide',
    data() {
      return {
        selected: 2,
        selectOptions: [2, 3, 4, 5, 6]
      }
    },
    computed: {
      grids: function () {
        return [...Array(this.selected).keys()]
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .layout {
    display: grid;
    grid-template-columns: 20% 1fr;
    grid-gap: 30px;
    padding: 30px;
  }

  .generator-select {
    width: 100%;
    cursor: pointer;
    border-radius: 3px;
    border: 1px solid #888;
    padding: 10px;
    font-size: 16px;
    font-weight: bold;
  }

  .grid-container {
    display: grid;
    grid-auto-flow: column;
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
