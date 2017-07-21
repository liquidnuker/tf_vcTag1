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
  
  </div>
</template>
<script>
// import comp1 from "./Comp1.vue";
// import comp2 from "./Comp2.vue";

const comp1 = () => import('./Comp1.vue');
const comp2 = () => import('./Comp2.vue');

// with props
const comp4 = () => import('./Comp4.vue');

  export default {
    data () {
      return {   
        currentView: comp1,
        testMessage: "testmessageZ",
        url: "http://"
      }
    },
    components: {
      Comp1: comp1,
      Comp2: comp2,
      Comp4: comp4
    },
    mounted: function () {
      // console.log("Home.vue mounted");
    },
    methods: {
      changeView: function(component) {
        this.currentView = component;
      }
    }
  }
</script>

