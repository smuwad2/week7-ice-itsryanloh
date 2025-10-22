<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newItem: ""
            }
            
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <li v-for="(item, id) in items" :key="id">{{ item }}<button @click="items.splice(id, 1)">Delete!</button></li>
    <input v-model="newItem"><button @click="items.push(newItem); newItem=''">Add!</button></input>
   
</template>
