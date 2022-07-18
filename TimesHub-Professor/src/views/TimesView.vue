<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      times: [
        { id: "f6dc3488-c074-4ccd-87a3-b2efb0a803a8", nome: "Time 1" },
        { id: "ddafa58a-08dd-41bc-99c4-b4b421849737", nome: "Time 2" },
        { id: "f6dc3488-c074-4ccd-87a3-b2efb0a803a8", nome: "Time 3" },
        { id: "8954e791-4fb4-4cb2-a25c-0d0273544c22", nome: "Time 4" },
        { id: "d2f63ec8-fe4c-4d55-a95e-91b5389685d5", nome: "Time 5" },
      ],
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      if (this.novo_time !== "") {
        const novo_id = uuidv4();
        this.times.push({
          id: novo_id,
          nome: this.novo_time,
        });
        this.novo_time = "";
      }
    },
    excluir(time) {
      const indice = this.times.indexOf(time);
      this.times.splice(indice, 1);
    },
  },
};
</script>

<template>
  <div class="conteiner">
    <div class="title">
      <h2>Gereciamento de Times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-times"></div>
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Nome</th>
          <th>Acoes</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="time in times" :key="time.id">
          <td>{{ time.id }}</td>
          <td>{{ time.nome }}</td>
          <td>
            <button>Editar</button>
            <button @click="excluir(time)">Excluir</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
.title {
  margin: 2rem auto;
  display: flex;
  justify-content: center;
}

.form-input {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.form-input input {
  width: 60%;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 0 10px;
}

.form-input button {
  margin-left: 1%;
  width: 20%;
  height: 40px;
  border: 1px solid rgb(36, 127, 65);
  border-radius: 10px;
  background-color: rgb(36, 127, 65);
  color: white;
  font-weight: bold;
  cursor: pointer;
}

.list-times {
  display: flax;
  justify-content: center;
}

table {
  width: 50%;
  margin: 2% auto;
  border-collapse: collapse;
}

table tr th {
  border: 1px solid #ccc;
  padding: 10px;
  font-weight: bold;
}

table tr td {
  border: 1px solid #ccc;
  padding: 10px;
}

table tr:nth-child(odd) {
  background-color: #ccc;
  color: black;
}
</style>
