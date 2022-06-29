<template>
  <div id="app">
    <h1 class="fw-bold">Crear nueva tarea</h1>
    <hr />
    <img
      class="rounded mx-auto d-block mb-3"
      alt="Tareas"
      width="300px"
      height="300px"
      src="../src/assets/tareas.jpg"
    />
    <label>
      <strong class="fs-5">Tarea</strong>
      <input
        class="mx-2 mb-3"
        type="text"
        v-model="tarea"
        placeholder="Ingrese una nueva tarea"
      />
    </label>
    <button @click="addTarea" class="bg-primary text-white">Crear</button>

    <ul v-for="(tarea, index) in tareas" :key="index">
      <li>
        <strong> {{ index }}: {{ tarea }} </strong>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tarea: "",
      tareas: [],
    };
  },
  methods: {
    addTarea() {
      const { tarea } = this;
      this.tareas.push(tarea);
      this.tarea = "";
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 100px;
  background-color: rgb(202, 179, 223);
}
</style>
