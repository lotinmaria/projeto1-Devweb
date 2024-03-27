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
        <input class="input-user" type="email" placeholder="Email"  />
        <input class="input-user" type="password" placeholder="Senha"  />
        <input class="input-user" type="password" placeholder="Confirma Senha"  />
        <select name="estados" id="estados">
          <option value="">Acre</option>
          <option value="">Alagoas</option>
          <option value="">Amapá</option>
          <option value="">Amazonas</option>
          <option value="">Bahia</option>
          <option value="">Ceará</option>
          <option value="">Espírito Santo</option>
          <option value="">Goiás</option>
          <option value="">Maranhão</option>
          <option value="">Mato Grosso</option>
          <option value="">Mato Grosso do Sul</option>
          <option value="">Minas Gerais</option>
          <option value="">Pará</option>
          <option value="">Paraíba</option>
          <option value="">Paraná</option>
          <option value="">Penambuco</option>
          <option value="">Piauí</option>
          <option value="">Rio de Janeiro</option>
          <option value="">Rio Grande do Norte</option>
          <option value="">Rio Grande do Sul</option>
          <option value="">Rondônia</option>
          <option value="">Roraima</option>
          <option value="">Santa Catarina</option>
          <option value="">São Paulo</option>
          <option value="">Sergipe</option>
          <option value="">Tocantins</option>
          <option value="">Distrito Federal</option>
        </select>
        <input class="input-user" type="text" placeholder="Cidade"  />
        <input class="input-user" type="text" placeholder="Endereço"  />
        <input class="input-user" type="text" placeholder="Hobbies" />
        <input class="input-user" type="date" placeholder="Data de nascimento"  />
        <label for="">Linguagem de programação favorita</label>
      <input class="input-user" type="radio" value="JavaScript" />
      <input class="input-user" type="text" placeholder="Biografia" />
      <input class="input-button" type="submit" name="cuceta" id="pinto" />
    </form>
  </div>
  
  <div class="resultado">
    <h1>Resultado</h1>
    <div class="conteudo">  
      <div class="infos">{{ usuario.nome }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
      <div class="infos">{{ usuario }}</div>
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
