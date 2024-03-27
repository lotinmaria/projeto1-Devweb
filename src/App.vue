<script setup>
const usuario = {
  nome: '',
  email: '',
  senha: '',
  cidade: '',
  estado: '',
  hobbies: '',
  programacao: '',
  biografia: ''
}
const confirmaSenha = ''

const senhaConfirmada = usuario.senha == confirmaSenha ? true : false
</script>

<template>
  <main>  
    <div class="form">
      <form class="form-info" action="">
        <h1 class="titulo">Formulário</h1>
        <input class="input-user" type="text" placeholder="Nome" required />
        <input class="input-user" type="text" placeholder="Data de nascimento" required />
        <input class="input-user" type="email" placeholder="Email" required />
        <input class="input-user" type="password" placeholder="Senha" required />
        <input class="input-user" type="password" placeholder="Confirma Senha" required />
        <input class="input-user" type="text" placeholder="Cidade" required />
        <input class="input-user" type="select" placeholder="Estado" required />
        <input class="input-user" type="text" placeholder="Endereço" required />
        <input class="input-user" type="text" placeholder="Hobbies" />
      <label for="">Linguagem de programação favorita</label>
      <input class="input-user" type="radio" value="JavaScript" />
      <input class="input-user" type="text" placeholder="Biografia" />
      <input class="input-button" type="submit" name="" id="" />
    </form>
  </div>
  
  <div class="resultado">
    <h1>Resultado</h1>
    <div class="conteudo">
      conteúdo
    </div>


  </div>


</main>
</template>

<style scoped>
main{
  display: flex;
  justify-content: space-evenly;
}
.titulo {
  display: flex;
  justify-content: center;
  margin: 20px 0;
}
.form {
  display: flex;
  justify-content: center;
}
.form-info {
  background-color: rgb(107, 158, 141);
  width: 20vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 3px solid black;
  border-radius: 10px;
  padding: 1% 2%;
  gap: 8px;
}
.input-user {
  background-color: rgb(237, 229, 245);
  border: 2px solid black;
  padding: 2px 0 2px 5px;
  border-radius: 5px;
}
.input-user::placeholder {
  color: rgba(27, 27, 27, 0.678);
}
.input-button {
  background-color: rgb(14, 44, 33);
  color: aliceblue;
  padding: 5px 10px;
  border: 3px solid black;
  border-radius: 10px;
}
.resultado{
  background-color: rgb(107, 158, 141);
  width: 20vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 3px solid black;
  border-radius: 10px;
  padding: 1% 2%;
  gap: 8px;
}
</style>
