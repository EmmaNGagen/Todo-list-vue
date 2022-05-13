<template>
  <div class="todoApp">
    <header>
      <h1 class="title">Things to do</h1>
    </header>
    <section class="taskSection">
      <div class="inputSection">
        <AddTodo :Heading="headingToSend" @addTodo="handleAddTodo($event)" />
      </div>
      <div class="todoSection">
        <div id="tasks" class="todos" v-for="(todo, i) in listOfTodos" :key="i">
          <div>
            <label
              :class="[{ done: todo.done }]"
              @click="
                () => {
                  checkedDone(todo);
                }
              "
              id="checkbox"
              type="checkbox"
            >
              <input id="inputChecked" type="checkbox" />

              {{ todo.title }}
            </label>
          </div>

          <div
            class="x"
            @click="
              () => {
                removeTask(i);
              }
            "
          >
            <img src="./../assets/close-symbol.svg" alt="close" />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { Todo } from "./../models/Todo";
import AddTodo from "./AddTodo.vue";

@Options({
  components: {
    AddTodo,
  },
})
export default class TodoList extends Vue {
  headingToSend = "Add to your list";
  //isDone = false; nej

  listOfTodos: Todo[] = [
    new Todo("Learn React", false),
    new Todo("Push to git", false),
    new Todo("Update Visual studio code", false),
  ];

  handleAddTodo(t: Todo) {
    console.log("hello from todo-List", t);
    this.listOfTodos.push(t);
  }

  checkedDone(todo: Todo) {
    todo.done = !todo.done;
  }

  removeTask(i: number) {
    this.listOfTodos.splice(i, 1);
  }
}
</script>

<style lang="scss">
@media only screen and (min-width: 1091px) and (max-width: 4000px) {
  .todoApp {
    header {
      padding-top: 66px;
      padding-bottom: 33px;
    }
    .title {
      color: rgb(0, 0, 0);
      font-weight: 800;
      font-size: 40px;
      text-transform: uppercase;
      margin: 0;
    }
    h3 {
      font-size: 20px;
      margin: 0;
      padding-bottom: 15px;
    }
  }

  .taskSection {
    display: flex;
    flex-direction: column;

    .inputSection {
      display: flex;
      flex-direction: column;
      position: relative;
      align-content: center;
      align-items: center;
      text-align: center;
      margin: auto;
      width: 25%;
      border-radius: 6px;
      padding: 20px;
    }
    .todoSection {
      display: flex;
      flex-direction: column;
      align-content: center;
      margin: auto;
      width: 45%;
      border-radius: 6px;
      padding: 20px;
      background-color: #9b63c9b2;
      box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;

      #inputChecked {
        cursor: pointer;
      }
      .done {
        text-decoration: line-through;
      }

      .todos {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 5px;
        font-size: 20px;
      }

      .x {
        cursor: pointer;
      }
    }
  }

  .removeTaskDiv {
    display: flex;
    justify-content: space-between;
  }
}

@media only screen and (min-width: 701px) and (max-width: 1090px) {
  .todoApp {
    header {
      padding-top: 66px;
      padding-bottom: 33px;
    }
    .title {
      color: rgb(0, 0, 0);
      font-weight: 800;
      font-size: 40px;
      text-transform: uppercase;
      margin: 0;
    }
    h3 {
      font-size: 20px;
      margin: 0;
      padding-bottom: 15px;
    }
  }

  .taskSection {
    display: flex;
    flex-direction: column;

    .inputSection {
      display: flex;
      flex-direction: column;
      position: relative;
      align-content: center;
      align-items: center;
      text-align: center;
      margin: auto;
      width: 25%;
      border-radius: 6px;
      padding: 20px;
    }
    .todoSection {
      display: flex;
      flex-direction: column;
      align-content: center;
      margin: auto;
      width: 50%;
      border-radius: 6px;
      padding: 20px;
      background-color: #9b63c9b2;
      box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;

      #inputChecked {
        cursor: pointer;
      }
      .done {
        text-decoration: line-through;
      }

      .todos {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 5px;
        font-size: 20px;
      }

      .x {
        cursor: pointer;
      }
    }
  }

  .removeTaskDiv {
    display: flex;
    justify-content: space-between;
  }
}

@media only screen and (max-width: 700px) {
  .todoApp {
    header {
      padding-top: 66px;
      padding-bottom: 33px;
    }
    .title {
      color: rgb(0, 0, 0);
      font-weight: 800;
      font-size: 40px;
      text-transform: uppercase;
      margin: 0;
    }
    h3 {
      font-size: 20px;
      margin: 0;
      padding-bottom: 15px;
    }
  }

  .taskSection {
    display: flex;
    flex-direction: column;

    .inputSection {
      display: flex;
      flex-direction: column;
      position: relative;
      align-content: center;
      align-items: center;
      text-align: center;
      margin: auto;
      width: 25%;
      border-radius: 6px;
      padding: 20px;
    }
    .todoSection {
      display: flex;
      flex-direction: column;
      align-content: center;
      margin: auto;
      width: 70%;
      border-radius: 6px;
      padding: 20px;
      background-color: #9b63c9b2;
      box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;

      #inputChecked {
        cursor: pointer;
      }
      .done {
        text-decoration: line-through;
      }

      .todos {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 5px;
        font-size: 20px;
      }

      .x {
        cursor: pointer;
      }
    }
  }

  .removeTaskDiv {
    display: flex;
    justify-content: space-between;
  }
}
</style>
