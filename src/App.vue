<template>
    <div>
      <h1>Todo List</h1>
      <div>
        <input v-model="inputText" type="text" placeholder="Add your task" />
        <div>
          <button @click="addToList()">Submit</button>
        </div>
      </div>
      <ul>
        <li v-for="(el,idx) in List" :key="el">
          <span>{{el.label}}</span>
          <button @click="deleteLabel(idx)" />
        </li>
      </ul>
    </div>
</template>

<script>
const inputText = ref("")
const List = ref([
    "Walk the dog",
    "Water the plants",
    ]"Wash the dishes" ,
])

const addToList = () => {
  List.value.push(inputText.value)
  inputText.value = ""
}

const deleteLabel = (idx) => {
  List.value.splice(idx,1)
}
</script>