<template>
  <div class="container" id="app">
    <div class="container-formulario logar-container" v-if="!logado">
      <form action="#">
        <img
          class="imag"
          src="./assets/vamos.png"
          alt="some text"
          width="240"
          height="200"
        />
        <div nome="email">
          <label>E-mail:</label>
          <input
            type="email"
            v-model="email"
            placeholder="Digite seu E-mail:"
            required
          />
        </div>
        <div nome="senha">
          <label>Senha:</label>
          <input
            type="password"
            v-model="senha"
            placeholder="Digite sua senha:"
            required
          />
        </div>
        <button @click="entrar">Entrar</button>
        
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
export default {
  data() {
    return {
      nome: "",
      email: "",
      senha: "",
      logado: false,
      deslogado: false
    };
  },
  methods: {
    entrar() {
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
  margin: -20px 0 50px;
  margin-left: 400px;
}

h1 {
  font-weight: bold;
  margin: 10;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #ff4e50;
  color: -webkit-linear-gradient(to right, #f9d423, #ff4e50);
  color: linear-gradient(to right, #f9d423, #ff4e50);
}

label {
  color: #d1b10f;
  color: -webkit-linear-gradient(to right, #f9d423, #ff4e50);
  color: linear-gradient(to right, #f9d423, #ff4e50);
  font-weight: 600;
  margin: 100px 10px 100px 10px;
}

a {
  color: #333;
  font-size: 14px;
  text-decoration: none;
  margin: 15px 0;
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
  padding: 30px;
  margin: 5px;
  text-align: center;
}
.container-logado {
  background-color: #ffffff;
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  margin-right: 380px;
  margin-top: 180px;

}

input {
  background-color: #eee;
  border: 1px solid black;
  padding: 12px;
  margin: 8px;
  width: 100%;
}

.container {
  border-radius: 10px;
  position: relative;
  width: 768px;
  max-width: 100%;
  min-height: 480px;
}

.container-formulario {
  position: absolute;
  height: 100%;
}

.logar-container {
  width: 50%;
  z-index: 2;
}
.lembre-se {
  justify-content: space-around;
}
</style>
