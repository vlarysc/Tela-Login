<template>
  <div class="container" id="app">
    <div class="container-formulario logar-container">
      <form action="#">
        <h1>Tela de Login</h1>
        <div>
          <label>Nome:</label>
          <input
            type="text"
            v-model="nome"
            name="nome"
            placeholder="Digite seu nome:"
          />
        </div>
        <div>
          <label>E-mail:</label>
          <input
            type="email"
            v-model="email"
            placeholder="Digite seu E-mail:"
          />
        </div>
        <div>
          <label>Senha:</label>
          <input
            type="password"
            v-model="senha"
            placeholder="Digite sua senha:"
          />
        </div>
        <button @click="enviar">Entrar</button>
        <div class="lembre-se">
          <label>Lembre-se</label>
          <input type="checkbox" v-model="senha"           
          />
        </div>
        
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
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  background: #f09819;
  background: -webkit-linear-gradient(to right, #edde5d, #f09819);
  background: linear-gradient(to right, #edde5d, #f09819);

  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
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
  color: #ff4e50;
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
  background: #ff4e50; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #f9d423,
    #ff4e50
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #f9d423,
    #ff4e50
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

button:active {
  transform: scale(0.95);
}

button:focus {
  outline: none;
}

button.ghost {
  background-color: transparent;
  border-color: #ffffff;
}

form {
  background-color: #ffffff;
  border-radius: 50px;
  display: block;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 50px;
  margin: 30px;
  text-align: center;
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
  overflow: hidden;
  width: 768px;
  max-width: 100%;
  min-height: 480px;
}

.container-formulario {
  position: absolute;
  top: 0;
  height: 100%;
  transition: all 0.6s ease-in-out;
}

.logar-container {
  left: 0;
  width: 50%;
  z-index: 2;
}

.container.right-panel-active .logar-container {
  transform: translateX(100%);
}

.sign-registrar-container {
  left: 0;
  width: 50%;
  opacity: 0;
  z-index: 1;
}

.container.right-panel-active .registrar-container {
  transform: translateX(100%);
  opacity: 1;
  z-index: 5;
  animation: show 0.6s;
}

@keyframes show {
  0%,
  49.99% {
    opacity: 0;
    z-index: 1;
  }

  50%,
  100% {
    opacity: 1;
    z-index: 5;
  }
}

.redes-sociais {
  margin: 20px 0;
}

.redes-sociais a {
  border: 1px solid #dddddd;
  border-radius: 50%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  margin: 0 5px;
  height: 40px;
  width: 40px;
}

.lembre-se {	
justify-content: right;
}
</style>
