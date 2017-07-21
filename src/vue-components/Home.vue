<template>
  <div>

    <component v-bind:is="currentView" />

    <!-- ok -->
<!-- <component v-bind:is="currentView" 
:pr-message="testMessage"
:pr-url="url" /> -->

<Comp2 />
<button v-on:click="changeView('Comp2')">change</button>

<Comp4 :pr-message="testMessage"
:pr-url="url" />

<hr>
<div v-for="i in items">
  <p>{{ i.itemName }}</p>
</div>
<hr>

<button v-on:click="changeItem1()">changeItem1</button>

<Comp5 :pr-data="items"/>



</div>
</template>
<script>
import {store} from "../js/store.js";

const comp1 = () => import('./Comp1.vue');
const comp2 = () => import('./Comp2.vue');

// with props
const comp4 = () => import('./Comp4.vue');
const comp5 = () => import('./Comp5.vue');

  export default {
    data () {
      return {   
        currentView: comp1,
        testMessage: "testmessageZ",
        url: "http://",

        items: store.items

      }
    },
    components: {
      Comp1: comp1,
      Comp2: comp2,
      Comp4: comp4,
      Comp5: comp5
    },
    mounted: function () {
      // console.log("Home.vue mounted");
    },
    methods: {
      changeView: function(component) {
        this.currentView = component;
      },
      refresh: function() {
        // this.items = store.items;
      },
      changeItem1: function() {
        store.items[0].itemName = "zzzzzzzz";
      }
    }
  }
</script>

