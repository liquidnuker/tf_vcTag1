<template>
  <div>
    <hr>
    Comp5.vue <br>
    items: {{ prData.length }} <br>
    {{ prData }}
    
    <!-- changeable via Home.vue -->
    <ul v-for="i in prData">
      <li>{{ i.itemName }}</li>
    </ul>

    <hr>
    <button v-on:click="changeItem2">changeItem2</button>
    <button v-on:click="comp5delete">comp5delete</button>
  </div>
</template>
<script>
import {store} from "../js/store.js";

export default {
    data () {
      return {   
        
      }
    },
    props: [
    // connects to main item
      "prData"
    ],
    components: {
     
    },
    mounted: function () {
      
    },
    methods: {
      changeItem2: function() {
        store.items[0].itemName = "changed inside Comp5.vue";
      },
      comp5delete: function() {
        let itemToRemove = 0;
        store.items.splice(itemToRemove, 1);
      }
    }
  }
</script>