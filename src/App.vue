<template>
  <TodoList></TodoList>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TodoList from "./components/TodoList.vue";
@Options({
  components: {
    TodoList,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@media only screen and (min-width: 1091px) and (max-width: 4000px) {
  body {
    background: url(./assets/background.png);
    height: 760px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    margin: 0;
    padding: 0;
    border: 0;
    background-color: rgb(253, 254, 227);
    text-align: center;
    font-family: "Encode Sans Expanded", sans-serif;
  }
}
@media only screen and (min-width: 620px) and (max-width: 1090px) {
  body {
    background: url(./assets/background.png);
    height: 760px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    margin: 0;
    padding: 0;
    border: 0;
    background-color: rgb(253, 254, 227);
    text-align: center;
    font-family: "Encode Sans Expanded", sans-serif;
  }
}

@media only screen and (max-width: 620px) {
  body {
    background: url(./assets/background.png);
    height: 760px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    margin: 0;
    padding: 0;
    border: 0;
    text-align: center;
    font-family: "Encode Sans Expanded", sans-serif;
  }
}
</style>
