<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

const newItem = ref('')

function deleteItem(index) {
    items.value.splice(index, 1)
}

function addItem() {
    items.value.push(newItem.value)
    newItem.value = ''
}
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul>
        <li v-for="(item, index) in items" :key="index">{{ item }}
            <!-- <button @click="items.splice(index,1)">Delete</button> -->
            <button @click="deleteItem(index)">Delete</button>
        </li>
     </ul>

     <input type="text" name="newItem" v-model="newItem" @keyup.enter="addItem">
     <!-- <button @click="items.push(newItem)">Add!</button> -->
     <button @click="addItem()">Add!</button>
     

   
</template>
