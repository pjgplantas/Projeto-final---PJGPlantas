<template>
  <div>
    <br />
    <h2 id="AddPlantas">Adicionar planta</h2>
    <br />
    <b-form-input
      id="Input2"
      v-model="nome"
      placeholder="Informe o nome"
    ></b-form-input>
    <br />
    <b-form-input
      id="Input2"
      v-model="valor"
      placeholder="Informe o preço"
    ></b-form-input>
    <br />
    <b-button variant="outline-info" @click="salvar">{{ textoBotao }}</b-button>
    <br />
    <hr />
    <b-table
      striped
      hover
      :items="plantas"
      responsive
      :fields="fields"
      id="TablePlantas"
    >
      <template #cell(actions)="row">
        <b-button
          variant="danger"
          size="sm"
          class="mr-1"
          @click="deletar(row.item)"
        >
          <b-icon-trash-fill></b-icon-trash-fill>
        </b-button>
        <b-button size="sm" variant="info" @click="editar(row.item)">
          <b-icon-pencil-fill></b-icon-pencil-fill>
        </b-button> </template
    ></b-table>
  </div>
</template>

<script>
import {
  collection,
  getDocs,
  doc,
  setDoc,
  updateDoc,
  deleteDoc,
} from "firebase/firestore";
import { db } from "@/plugins/firebase";

export default {
  name: "Plantas",
  data() {
    return {
      fields: [
        { key: "nome", label: "Nome" },
        { key: "valor", label: "Valor" },
        { key: "actions", label: "Ações" },
      ],
      plantas: [],
      id: "",
      nome: "",
      valor: "",
      editting: false,
    };
  },
  computed: {
    textoBotao() {
      return this.editting ? "Salvar" : "Adicionar";
    },
  },
  methods: {
    async salvar() {
      if (this.editting) {
        const plantaRef = doc(db, "plantas", this.id);

        await updateDoc(plantaRef, {
          nome: this.nome,
          valor: this.valor,
        });
      } else {
        const plantasRef = collection(db, "plantas");
        await setDoc(doc(plantasRef), {
          nome: this.nome,
          valor: this.valor,
        });
      }

      this.buscarPlantas();
    },
    async buscarPlantas() {
      this.plantas = [];
      const querySnapshot = await getDocs(collection(db, "plantas"));
      querySnapshot.forEach((planta) => {
        // doc.data() is never undefined for query doc snapshots
        // console.log(planta.id, " => ", planta.data());
        this.plantas.push({ ...planta.data(), id: planta.id });
      });
    },
    editar(planta) {
      this.editting = true;
      this.id = planta.id;
      this.nome = planta.nome;
      this.valor = planta.valor;
    },
    async deletar(planta) {
      await deleteDoc(doc(db, "plantas", planta.id));
      this.buscarPlantas();
    },
  },
  created() {
    this.buscarPlantas();
  },
};
</script>

