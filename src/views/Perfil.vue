<template>
  <div>
    <b-container class="login-page" fluid>
      <b-row>
        <b-col>
          <b-col>
            <b-form
              class="formp"
              @submit.prevent="login"
              @reset="onReset"
              v-if="show"
            >
              <div class="parte1">
                <div class="imgperfil">
                  <img
                    class="rounded-circle mt-5"
                    width="150px"
                    src="https://st3.depositphotos.com/15648834/17930/v/600/depositphotos_179308454-stock-illustration-unknown-person-silhouette-glasses-profile.jpg"
                  />
                </div>
                <div class="NomeCliente">João</div>
                <div class="EmailCliente">jaumm.silva.04@gmail.com</div>
              </div>
              <div class="parte2"><hr class="HrForm" /></div>
              <div class="parte3">
                <div class="TituloPerfil">Configurações do Perfil</div>
                <div class="divs">Email</div>
                <b-form-group id="input-group-2">
                  <b-form-input id="input-2" v-model="form.email" required>
                  </b-form-input>
                </b-form-group>
                <div class="divs">Nome:</div>
                <b-form-group id="input-group-2">
                  <b-form-input
                    id="input-2"
                    type="name"
                    v-model="form.name"
                    required
                  ></b-form-input>
                </b-form-group>
                <div class="divs">Endereço:</div>
                <b-form-group id="input-group-2">
                  <b-form-input
                    id="input-2"
                    v-model="form.endereco"
                    required
                  ></b-form-input>
                </b-form-group>
                <div class="divs">Data de nascimento:</div>
                <b-form-group id="input-group-2">
                  <b-form-input
                    id="input-2"
                    type="date"
                    v-model="form.date"
                    required
                  ></b-form-input>
                </b-form-group>
                <div class="divs">Sexo:</div>
                <b-form-group class="forms" v-slot="{ ariaDescribedby }">
                  <b-form-radio
                    id="opt1"
                    v-model="selected"
                    :aria-describedby="ariaDescribedby"
                    name="some-radios"
                    value="A"
                    >Feminino</b-form-radio
                  >
                  <b-form-radio
                    id="opt2"
                    v-model="selected"
                    :aria-describedby="ariaDescribedby"
                    name="some-radios"
                    value="B"
                    >Masculino</b-form-radio
                  >
                </b-form-group>
                <b-button class="btncad" type="submit">Salvar perfil</b-button>
              </div>
            </b-form>
          </b-col>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "perfil",
  data() {
    return {
      form: {
        email: "",
        name: "",
        selected: "",
        endereco: "",
        date: "",
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.name = "";
      this.form.date = "";
      this.form.selected = " ";
      this.form.endereco = "";
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

.formp {
  border-radius: 2px;
  height: 98vh;
  width: 173vh;
  margin: 2% 0 0 5%;
  background-color: white;
  display: flex;
}
.login-page {
  width: 1950px;
  height: 1000px;
  background: #00bf8f;  /* fallback for old browsers */
background: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
.parte1 {
  margin: 2% 0 0 15%;
}
.NomeCliente {
  font-family: "Roboto", sans-serif;
  font-size: 25px;
  font-weight: 600;
  margin: 0 0% 0 24%;
}

.EmailCliente {
  color: black;
  opacity: 50%;
  font-size: 19px;
}
.HrForm {
  border: 1px solid #808080;
  height: 88vh;
}
.parte2 {
  margin: 3% 0 0 17%;
}
.parte3 {
  margin: 5% 0 0 10%;
}
.TituloPerfil {
  font-family: "Roboto", sans-serif;
  font-size: 2rem;
  color: black;
  padding: 0px;
  text-align: center;
}
.divs {
  color: black;
  font-style: normal;
  font-weight: 500;
  white-space: nowrap;
  font-size: 19px;
  margin: 10% 0 0 0;
}
.form-control {
  background: white;
  border-style: none none solid none;
  border-color: rgba(62, 150, 97, 0.95);
  width: 480px;
}
.btncad {
  background: #00bf8f;  /* fallback for old browsers */
background: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  border: 0;
  padding: 13px;
  width: 150px;
  font-size: 23px;
  border-radius: 10px;
  margin: 10% 0 0 32%;
}

@media (max-width: 844px) {
  .imgperfil {
    margin-left: 25%;
  }

  .login-page {
    width: 390px;
    height: 1230px;
    padding: 0;
  }
  .formp {
    width: 370px;
    flex-direction: column;
    height: 1200px;
    margin-left: 6%;
  }
  .parte1 {
    width: 300px;
    height: 380px;
    justify-content: center;
    margin-left: 30px;
  }
  .NomeCliente {
    text-align: center;
    margin: 0px;
  }
  .EmailCliente {
    text-align: center;
    margin: 0px;
  }

  .parte3 {
    width: 320px;
    height: 700px;
    margin-left: 30px;
    font-size: 10px;
  }
  .Titulo2Perfil {
    font-size: 20px;
  }
  .divs {
    font-size: 18px;
  }
  .form-control {
    width: 320px;
  }

  .parte5 {
    width: 300px;
    height: 400px;
    margin: 10% 0% 10% 8%;
  }
  .col {
    padding: 0px;
    margin: 0px;
    width: 390px;
  }
  .parte2 {
    display: none;
  }
  .parte4 {
    display: none;
  }

  .hrlay {
    display: none;
  }
  #footer {
    color: #3e9661;
    font-size: 16px;
    margin: 10% 10% 7% 5%;
    width: 340px;
  }
  .footer1 {
    margin: 3%;
    width: 250px;
    padding: 5%;
  }
  .footer2 {
    margin: 3%;
    width: 250px;
    padding: 5%;
  }
  .TituloPerfil {
    font-size: 20px;
  }
}
</style>
