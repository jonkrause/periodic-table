<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <p>
      <div id="cont" class="container">
        <div class="elements" v-bind:class="{
              nonmetal: element.groupBlock === nonmetal, 
              nobleGas: element.groupBlock === nobleGas, 
              alkaliMetal: element.groupBlock === alkaliMetal, 
              alkEarth: element.groupBlock === alkEarth, 
              metalloid: element.groupBlock === metalloid, 
              halogen: element.groupBlock === halogen, 
              alkaliMetal: element.groupBlock === alkaliMetal, 
              metal: element.groupBlock === metal, 
              transitionMetal: element.groupBlock === transitionMetal, 
              lanthanoid: element.groupBlock === lanthanoid, 
              actinoid: element.groupBlock === actinoid, 
              postTransitionMetal: element.groupBlock === postTransitionMetal, 
              lanthanoid: element.groupBlock === lanthanoid, 
              
              }" v-for="element in elements" :key="element.id">
          <p class="symbol">{{element.symbol}}</p>
          <p class="name">{{element.symbol}}</p>
        </div>
        <p>
          <div class="elements actinoid" v-for="bottom in table02" :key="bottom.id">
            <p class="symbol">{{bottom.symbol}}</p>
            <p class="name">{{bottom.symbol}}</p>
          </div>
          <p>
            <div class="bottom lanthanoid" v-for="last in table03" :key="last.id">
              <p class="symbol">{{last.symbol}}</p>
              <p class="name">{{last.symbol}}</p>
            </div>
          </p>
        </p>
      </div>
    </p>
  </div>
</template>

<script>
  import json from '../table.json';
  import table02 from '../table02.json';
  import table03 from '../table03.json';
  export default {
    name: 'app',
    data() {
      return {
        title: 'Periodic Table of the Elements',
        elements: json,
        table02: table02,
        table03: table03,
        nonmetal: "nonmetal",
        nobleGas: "noble gas",
        alkaliMetal: "alkali metal",
        alkEarth: "alkaline earth metal",
        metalloid: "metalloid",
        halogen: "halogen",
        alkaliMetal: "alkali metal",
        metal: "metal",
        transitionMetal: "transition metal",
        lanthanoid: "lanthanoid",
        actinoid: "actinoid",
        postTransitionMetal: "post-transition metal"
      }
    },
    methods: {
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  #cont {
    display: block;
    width: 1150px;
    text-align: center;
    margin: 0 auto;
  }
  #cont02 {
    display: block;
    width: 1150px;
    text-align: center;
    margin: 0 auto;
  }
  .elements {
    border: 1px solid lightgrey;
    margin: 5px;
    width: 50px;
    max-width: 5%;
    height: 50px;
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .bottom {
    border: 1px solid lightgrey;
    margin: 5px;
    width: 50px;
    max-width: 5%;
    height: 50px;
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    margin-top: -12px;
  }
  .symbol {
    font-size: 15px;
    font-weight: 500;
  }
  .lanthanoid {
    background-color: pink;
  }
  .actinoid {
    background-color: salmon;
  }
  .nonmetal {
    background-color: lightsteelblue;
  }
  .nobleGas {
    background-color: powderblue;
  }
  .alkaliMetal {
    background-color: peachpuff;
  }
  .alkEarth {
    background-color: coral;
  }
  .metalloid {
    background-color: lightskyblue;
  }
  .halogen {
    background-color: palevioletred;
  }
  .alkaliMetal {
    background-color: lightyellow;
  }
  .metal {
    background-color: lightcyan;
  }
  .transitionMetal {
    background-color: cornsilk;
  }
  .postTransitionMetal {
    background-color: gainsboro;
  }
  .elements:nth-child(n+2):nth-child(-n+17),
  .elements:nth-child(n+21):nth-child(-n+30),
  .elements:nth-child(n+39):nth-child(-n+48) {
    border: 1px solid #fff;
  }
  h1,
  h2 {
    font-weight: normal;
  }
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
  }
</style>
