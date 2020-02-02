<template>
  <div>
    <label class="d-flex align-items-center">
      Todo:
      <input class="form-control" type="text" placeholder="Enter what you want to do here..." v-model="toDo" v-on:keyup.enter="addToDo">
      <button type="button" class="btn btn-primary" role="button" @click="addToDo">ADD</button>
    </label>
    <table class="table">
      <thead>
      <tr>
        <th scope="col">Todo</th>
        <th scope="col">Actions</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(list, index) in toDoLists" :key="index">
        <template v-if="list.status === 'Done'">

          <td>
            <!-- Add order number to the list -->
            <!-- List's status is "Done", the text with deleted part -->
            <del>{{index+1 + "." + " " + list.toDo}}</del>
          </td>
          <td>
            <!-- List's status is "Done", the action have only remove -->
            <button type="button" class="btn btn-danger" role="button" @click="removeList">Remove</button>
          </td>
        </template>
        <template v-else-if="list.status === 'Edit'">
          <td>
            <label class="d-flex align-items-center">
              <!-- List's status is Edit, Change the text to input tag for edit -->
              <input class="form-control" type="text" placeholder="Enter what you want to do here..." v-model="list.toDo" v-on:keyup.enter="list.status = 'Todo'">
              <button type="button" class="btn btn-success" role="button" @click="list.status = 'Todo'">Done</button>
            </label>
          </td>
          <td>
            <!-- List's status is "Edit", the action have only remove -->
            <button type="button" class="btn btn-danger" role="button" @click="removeList(index)">Remove</button>
          </td>
        </template>
        <template v-else>
          <!-- Add order number to the "list" -->
          <td>{{index+1 + "." + " " + list.toDo}}</td>
          <td>
            <button type="button" class="btn btn-success" role="button" @click="doneList(index)">Done</button> |
            <button type="button" class="btn btn-primary" role="button" @click="editList(index)">Edit</button> |
            <button type="button" class="btn btn-danger" role="button" @click="removeList(index)">Remove</button>
          </td>
        </template>

      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    name: "question2",
    data() {
      return {
        toDoLists: [
          {
            toDo: "Buy KitKat",
            status: "Done"
          },
          {
            toDo: "Go to Senna Labs at 2 P.M.",
            status: "Todo"
          },
          {
            toDo: "Workout at 5 P.M.",
            status: "Todo"
          },
          {
            toDo: "Give a flower to June",
            status: "Done"
          }
        ],
        toDo: ""
      }
    },
    methods: {
      addToDo() {
        if (this.toDo !== "") {
          // Add to do list and set status of the list is "Todo"
          this.toDoLists.push({
            toDo: this.toDo,
            status: "Todo"
          });
          this.toDo = "";
        }
      },
      removeList(index) {
        // Remove the list
        this.toDoLists.splice(index, 1)
      },
      doneList(index) {
        // Change status of the list to "Done"
        this.toDoLists[index].status = 'Done';
      },
      editList(index) {
        // Change status of the list to "Edit"
        this.toDoLists[index].status = 'Edit';
      },
    }
  }
</script>

<style scoped>

</style>