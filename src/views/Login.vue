<template>
  <body>
    <b-container class="login-page" fluid>
      <b-row align-v="center">
        <b-col class="log">
          <div class="logo">
            <img src="../assets/images/logoopjgnovo.png" />
          </div>
        </b-col>
        <b-col>
          <b-form
            class="cform"
            @submit.prevent="login"
            @reset="onReset"
            v-if="show"
            ><div class="dlogin">PJG Plantas</div>
            <div class="emsen">Email:</div>
            <b-form-group id="input-group-1">
              <b-form-input
                v-model="form.email"
                type="email"
                style="
                  background: white;
                  border-style: none none solid none;
                  border-color: rgba(62, 150, 97, 0.95);
                "
                placeholder="Insira seu email"
              >
              </b-form-input>
            </b-form-group>
            <div class="emsen">Senha:</div>
            <b-form-group id="input-group-1">
              <b-form-input
                type="password"
                v-model="form.password"
                required
                style="
                  background: white;
                  border-style: none none solid none;
                  border-color: rgba(62, 150, 97, 0.95);
                "
                placeholder="Insira sua senha"
              ></b-form-input>
            </b-form-group>
            <div class="Ircad">
              <a href="/cadastro"> Não tem conta? Crie a sua aqui </a>
            </div>
            <div class="buttons">
              <b-button class="btncad" type="submit">Logar</b-button>
              <b-button class="btncad2">Administrar</b-button>
            </div>
          </b-form>
        </b-col>
      </b-row>
    </b-container>
  </body>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
      show: true,
    };
  },
  methods: {
    login() {
      if (
        this.form.email === "admin@admin.com" &&
        this.form.password === "admin"
      ) {
        alert("ok");
        this.$router.push("/");
      } else {
        alert("Email ou senha incorretos");
      }
      // const provider = new GoogleAuthProvider();
      // const auth = getAuth();
      // signInWithPopup(auth, provider)
      //   .then(() => {
      //     // This gives you a Google Access Token. You can use it to access the Google API.
      //     // const credential = GoogleAuthProvider.credentialFromResult(result);
      //     // const token = credential.accessToken;
      //     // The signed-in user info.
      //     // const user = result.user;
      //     // ...
      //     this.$router.push({ name: 'Home' });
      //   })
      //   .catch((error) => {
      //     console.log(error);
      //     // // Handle Errors here.
      //     // const errorCode = error.code;
      //     // const errorMessage = error.message;
      //     // // The email of the user's account used.
      //     // const email = error.email;
      //     // // The AuthCredential type that was used.
      //     // const credential = GoogleAuthProvider.credentialFromError(error);
      //     // ...
      //   });
    },
  },
  onReset(event) {
    event.preventDefault();
    // Reset our form values
    this.form.email = "";
    this.form.name = "";
    this.form.checked = [];
    // Trick to reset/clear native browser form validation state
    this.show = false;
    this.$nextTick(() => {
      this.show = true;
    });
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

.logo img {
  width: 400px;
  height: 400px;
}

.logo {
  margin: 20% 0 0 30%;
}

.login-page {
  height: 100vh;
  font-family: Jomolhari;
}
.cform {
  background-color: white;
  border-radius: 8px;
  margin: 20% 40% 0 10%;
  padding: 50px;
  width: 500px;
  height: 500px;
  align-items: center;
  box-shadow: 0px 4px 10px 10px rgba(15, 52, 6, 0.42);
}
span {
  padding: 0 10px;
}
body {
 background: #00bf8f;  /* fallback for old browsers */
background: -webkit-linear-gradient(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to top, #001510, #00bf8f); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}
.dlogin {
  font-size: 35px;
  line-height: 29px;
  text-align: center;
  margin: 5% 0 0 0;
}
a {
  color: #0000cd;
  text-decoration: none;
  font-size: 15px;
  font-weight: 600;
  margin: 3% 0 0 1%;
  font-family: "Roboto", sans-serif;
}
a:hover {
  color: #0000cd;
  opacity: 50%;
  text-decoration: none;
}
.btncad {
  background: #00bf8f;  /* fallback for old browsers */
background: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  border: 0;
  padding: 10px;
  width: 130px;
  font-size: 21px;
  border-radius: 4px;
  margin: 10% 0 0 10%;
  font-family: "Roboto", sans-serif;
}
.btncad:hover {
  background-color: #3e9661;
}
.emsen {
  padding: 8px;
  margin: 10% 0 0 0;
  font-size: 20px;
}
.btncad2 {
 background: #00bf8f;  /* fallback for old browsers */
background: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  border: 0;
  padding: 10px;
  width: 150px;
  font-size: 21px;
  font-weight: 500;
  border-radius: 4px;
  margin: 10% 0 0 10%;
  font-family: "Roboto", sans-serif;
}
.btncad2:hover {
  background-color: #3e9661;
}
.titulo {
  position: absolute;
  color: #fff7f7;
  font-size: 80px;
  font-weight: 500;
  line-height: 70px;
  mix-blend-mode: screen;
  font-family: Jomolhari;
  margin: 0 0 0 35%;
}
.form-control {
  padding: 1;
  font-size: 16px;
  font-weight: bold;
  margin: 0% 5% 0 0;
}

@media (max-width: 844px) {
  .cform {
    width: 350px;
    margin: 70% 0% 0 0;
  }
  .form-control {
    margin: 3% 5% 0 0%;
    padding: 1px;
  }

  .titulo {
    margin: 15% 0 0 20%;
  }
  .row {
    margin: 0% 20% 0% 2%;
  }
  .container-fluid {
    width: 100%;
    padding-right: 0;
    padding-left: 0;
    margin-right: 0;
    margin-left: 0;
  }
  .buttons {
    display: flex;
    margin: 15% 13% 0 0;
  }
  .btncad {
    padding: 10px;
    height: 50px;
    width: 100px;
  }
  .btncad2 {
    padding: 10px;
    height: 50px;
  }
}
</style>
