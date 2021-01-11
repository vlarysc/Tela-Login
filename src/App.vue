<template>
  <div class="container" id="app">
    <div class="container-formulario logar-container" v-if="!logado">
      <form action="#">
        <img
          class="imag"
          src="./assets/meuPlano.png"
          alt="some text"
          width="250"
          height="100"
        />
        <div class="email" nome="email">
          <label>E-mail: </label>
          <input          
            type="email"
            v-model="email"
            placeholder="Digite seu E-mail:"
            required
          />
        </div>
        <div class="senha" nome="senha">
          <label>Senha:</label>
          <input
            type="password"
            v-model="senha"
            placeholder="Digite sua senha:"
            required
          />
        </div>
        <button type="submit" @click="entrar">Entrar</button>
        

        <br>

        <RedesSociais />  

      </form>
    </div>
    <div class="container-logado" v-else>
    <form action="#">
      <h2>Logado</h2>

      <button @click="sair" padding="5px" >Sair</button>      
    </form>
    </div>
  </div>
</template>

<script>
import RedesSociais from './components/RedesSociais'

export default {
  components: { RedesSociais },
  data() {
    return {
      email: "",
      senha: "",
      logado: false,
    };
  },
  methods: {
    entrar() {
      if(this.email == "" || this.senha == "") {
        return ;
      }
      this.logado = true
    },
    sair() {
      this.logado = false
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background: #f09819;
  background: -webkit-linear-gradient(to right, #edde5d, #f09819);
  background: linear-gradient(to right, #edde5d, #f09819);

  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

label {
  color: #d1b10f;
  color: -webkit-linear-gradient(to right, #f9d423, #ff4e50);
  color: linear-gradient(to right, #f9d423, #ff4e50);
  font-weight: 600;
  width: 52px;
  display: inline-block;
  margin: 0px 10px 10px 45px;
  text-align: initial;
  width: 100%;
}


button {
  border-radius: 20px;
  border: 1px solid #ff4b2b;
  background-color: #ff4b2b;
  color: #ffffff;
  font-size: 12px;
  font-weight: bold;
  padding: 12px 45px;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: transform 80ms ease-in;
  background: #ff4e50;
  background: -webkit-linear-gradient(to right, #f9d423, #ff4e50);

  background: linear-gradient(to right, #f9d423, #ff4e50);
  margin: 10px 0;
}

button:active {
  transform: scale(0.95);
}

button:focus {
  outline: none;
}

button.ghost {
  background-color: transparent;
  border-color: #130b0b;
}

form {
  background-color: #ffffff;
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 20px 30px 40px;
  text-align: center;
}
.senha {
      margin: 10px 0;
       width: 100%;
}
.email {
      width: 100%;
}
.container-logado {
  background-color: #ffffff;
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;

}

input {
  background-color: rgb(255, 255, 255);
  border: 1px solid rgb(207, 207, 207);
  padding: 12px;
  width: 80%;  
  outline: none;
  border-radius: 50px;
}

.container {
  border-radius: 10px;
  width: 368px;
}

.imag {
  margin-top: 20px;
}

</style>
