<template>
  <div>
    <div class="heading">
      {{ Heading }}
    </div>
    <div class="inputDiv">
      <input
        class="textInput"
        type="text"
        placeholder="ToDo..."
        v-model="Todo"
        @keypress.enter="handleClick"
      />

      <button
        @click="
          () => {
            handleClick();
          }
        "
      >
        +
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { Todo } from "@/models/Todo";
import { Prop } from "vue-property-decorator";
import { Vue } from "vue-class-component";

export default class AddTodo extends Vue {
  @Prop() Heading!: string;

  Todo = "";

  handleClick() {
    this.$emit("addTodo", new Todo(this.Todo, false));
    this.Todo = "";
  }
}
</script>

<style lang="scss">
@media only screen and (min-width: 1091px) and (max-width: 4000px) {
  .heading {
    font-size: x-small;
    padding: 10px;
  }
  .inputDiv {
    display: flex;
    align-items: center;
  }

  .textInput {
    font-size: 18px;
    padding: 10px 10px 10px 10px;
    width: 250px;
    height: 30px;
    border-radius: 3px;
    border: 2px solid #9b63c9;
  }

  button {
    background: #9b63c9;
    position: relative;
    font-weight: bold;
    -webkit-border-radius: 1.5vw;
    line-height: 3vw;
    width: 30%;
    text-align: center;
    font-size: 33px;
    text-transform: lowercase;
    color: rgb(0, 0, 0);
    border: none;
    background-size: 200% auto;
    transition: 0.5s;
    -moz-animation-duration: 3s;
    margin: 5px;
    cursor: pointer;
  }

  button:hover {
    background-position: right center;
    color: #fff;
    text-decoration: none;
  }
}

@media only screen and (min-width: 701px) and (max-width: 1090px) {
  .heading {
    font-size: x-small;
    padding: 10px;
  }
  .inputDiv {
    display: flex;
    align-items: center;
  }

  .textInput {
    font-size: 18px;
    padding: 10px 10px 10px 10px;
    width: 250px;
    height: 30px;
    border-radius: 3px;
    border: 2px solid #9b63c9;
  }

  button {
    background: #9b63c9;
    position: relative;
    font-weight: bold;
    -webkit-border-radius: 2.5vw;
    line-height: 5vw;
    width: 30%;
    text-align: center;
    font-size: 33px;
    text-transform: lowercase;
    color: rgb(0, 0, 0);
    border: none;
    background-size: 200% auto;
    transition: 0.5s;
    -moz-animation-duration: 3s;
    margin: 5px;
    cursor: pointer;
  }

  button:hover {
    background-position: right center;
    color: #fff;
    text-decoration: none;
  }
}

@media only screen and (max-width: 700px) {
  .heading {
    font-size: x-small;
    padding: 10px;
  }
  .inputDiv {
    display: flex;
    align-items: center;
  }

  .textInput {
    font-size: 18px;
    padding: 10px 10px 10px 10px;
    width: 250px;
    height: 30px;
    border-radius: 3px;
    border: 2px solid #9b63c9;
  }

  button {
    background: #9b63c9;
    position: relative;
    font-weight: bold;
    -webkit-border-radius: 4.5vw;
    line-height: 7vw;
    width: 30%;
    text-align: center;
    font-size: 33px;
    text-transform: lowercase;
    color: rgb(0, 0, 0);
    border: none;
    background-size: 200% auto;
    transition: 0.5s;
    -moz-animation-duration: 3s;
    margin: 5px;
    cursor: pointer;
  }

  button:hover {
    background-position: right center;
    color: #fff;
    text-decoration: none;
  }
}
</style>
