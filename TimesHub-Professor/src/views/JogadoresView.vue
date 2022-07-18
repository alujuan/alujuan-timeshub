<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      Jogadores: [
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          nome: "Jogador 1",
          time: "Time 1",
        },
        {
          id: "be262d33-0280-4248-b5ee-22a4a5a2c02f",
          nome: "Jogador 2",
          time: "Time 1",
        },
        {
          id: "d11afe3d-ef1f-41bd-9b94-38d4aed6e93d",
          nome: "Jogador 3",
          time: "Time 1",
        },
        {
          id: "e3f4704a-fe1b-4411-b86e-92248f2e0714",
          nome: "Jogador 4",
          time: "Time 1",
        },
        {
          id: "a1555523-6c24-4748-9493-394b075e798e",
          nome: "Jogador 5",
          time: "Time 1",
        },
      ],
      novo_jogador: "",
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.Jogadores.push({
        id: novo_id,
        nome: this.novo_jogador,
        time: this.novo_time,
      });
    },
  },
};
</script>

<template>
  <div class="conteiner">
    <div class="title">
      <h2>Gereciamento de Jogador</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_jogador" />
      <input type="text" v-model="novo_time" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-Jogadores"></div>
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Nome</th>
          <th>Acoes</th>
          <th>Time</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="Jogador in Jogadores" :key="Jogador.id">
          <td>{{ Jogador.id }}</td>
          <td>{{ Jogador.nome }}</td>
          <td>{{ Jogador.time }}</td>
          <td>??</td>
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

.list-Jogadores {
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
