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
          <td><del>{{index+1 + "." + " " + list.toDo}}</del></td>
          <td>
            <button type="button" class="btn btn-danger" role="button" @click="removeList">Remove</button>
          </td>
        </template>
        <template v-else-if="list.status === 'Edit'">
          <td>
            <label class="d-flex align-items-center">
              <input class="form-control" type="text" placeholder="Enter what you want to do here..." v-model="list.toDo" v-on:keyup.enter="list.status = 'Todo'">
              <button type="button" class="btn btn-success" role="button" @click="list.status = 'Todo'">Done</button>
            </label>
          </td>
          <td>
<!--            <button type="button" class="btn btn-success" role="button" @click="doneList(index)">Done</button> |-->
<!--            <button type="button " class="btn btn-primary" role="button" @click="editList(index)">Edit</button> |-->
            <button type="button" class="btn btn-danger" role="button" @click="removeList(index)">Remove</button>
          </td>
        </template>
        <template v-else>
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
          this.toDoLists.push({
            toDo: this.toDo,
            status: "Todo"
          });
          this.toDo = "";
        }
      },
      removeList(index) {
        this.toDoLists.splice(index, 1)
      },
      doneList(index) {
        this.toDoLists[index].status = 'Done';
      },
      editList(index) {
        this.toDoLists[index].status = 'Edit';
      },
    }
  }
</script>

<style scoped>

</style>