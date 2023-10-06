<script setup>
import { ref } from 'vue'


const itemId = ref(0)
const shoppingitem = ref('')
const shoppinglist = ref([])
const shopped = ref(false)


function addItem() {
    shoppinglist.value.push({
        id: itemId.value++,
        item: shoppingitem.value,
        status: shopped.value
    })

    shoppingitem.value = ''
}

function removeItem(i) {
    shoppinglist.value = shoppinglist.value.filter((t) => t !== i)
}

//Composition API with SFC .vue`
</script>

<template>

    <div>
        <h1>My Shopping List</h1>
        <input type="text" v-model="shoppingitem">
        <button @click="addItem">Add Item</button>
        <ol>
            <li v-for="i in shoppinglist">
                <input type="checkbox" v-model="i.shopped">
                <span :class="{done: i.shopped}">{{ i.item }}</span>
                
                <button @click="removeItem(i)">X</button>
            </li>
        </ol>

    </div>
</template>

<style scoped>

div{
    width: 100%;
    height: 400px;
    background-color: black;
    color:white;
}

div h1, input, button, ol, li input, li span, li button{
    border-radius: 10px;
}

.done{
    text-decoration: line-through;
}

</style>