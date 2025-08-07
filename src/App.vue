<script setup>
import { ref } from 'vue';
import Heading from '@/components/heading.vue'
const inItem = ref("")
const cost= ref(0)
const total = ref(0)
const items = ref(
  [
    
  ]
)
function it_click(){
   items.value = [...items.value,
   {
    name: inItem.value,
    cost: cost.value
   }
   ]
   total.value += parseInt(cost.value)
   inItem.value = ""
   cost.value = 0

}
</script>

<template>
  <div class="project">
     <Heading :total="total"/>
     <div id="app">
     <ul v-for="item in items">
        <li>{{ item["name"] }} : {{ item["cost"] }}</li>
     </ul>
     <input type="text" v-model="inItem"></input>
     <input type="text" v-model="cost"></input>
     <button @click="it_click">Add</button>
     </div>
  </div>
 
  
</template>

<style scoped>
  body{
    display: "flex";
    flex-direction: row;
    align-items: center;
    height: 100vh;
    width:100%;
  }
  .project{
    text-align: center;
  }
  #app{
    display: "flex";
    justify-content: center;
    align-items: center;
    height: 100vh;
    width:100%;
  }
  h1,h2{
    text-align: center;
  }

</style>

