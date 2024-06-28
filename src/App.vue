<script setup>
import { reactive, ref } from 'vue'; 

const estados = ref([
  { sigla: 'AC', nome: 'Acre' },
  { sigla: 'AL', nome: 'Alagoas' },
  { sigla: 'AP', nome: 'Amapá' },
  { sigla: 'AM', nome: 'Amazonas' },
  { sigla: 'BA', nome: 'Bahia' },
  { sigla: 'CE', nome: 'Ceará' },
  { sigla: 'DF', nome: 'Distrito Federal' },
  { sigla: 'ES', nome: 'Espírito Santo' },
  { sigla: 'GO', nome: 'Goiás' },
  { sigla: 'MA', nome: 'Maranhão' },
  { sigla: 'MT', nome: 'Mato Grosso' },
  { sigla: 'MS', nome: 'Mato Grosso do Sul' },
  { sigla: 'MG', nome: 'Minas Gerais' },
  { sigla: 'PA', nome: 'Pará' },
  { sigla: 'PB', nome: 'Paraíba' },
  { sigla: 'PR', nome: 'Paraná' },
  { sigla: 'PE', nome: 'Pernambuco' },
  { sigla: 'PI', nome: 'Piauí' },
  { sigla: 'RJ', nome: 'Rio de Janeiro' },
  { sigla: 'RN', nome: 'Rio Grande do Norte' },
  { sigla: 'RS', nome: 'Rio Grande do Sul' },
  { sigla: 'RO', nome: 'Rondônia' },
  { sigla: 'RR', nome: 'Roraima' },
  { sigla: 'SC', nome: 'Santa Catarina' },
  { sigla: 'SP', nome: 'São Paulo' },
  { sigla: 'SE', nome: 'Sergipe' },
  { sigla: 'TO', nome: 'Tocantins' }
])

const hobbies = ref([
  'andar de bicicleta',
  'ler',
  'nadar',
  'correr',
  'programar',
  'dançar',
  'pintar',
  'ouvir música',
])

const usuario = reactive({
  nome: '',
  email: '',
  senha: '',
  cidade: '',
  endereco: '',
  estado: '',
  hobbies: [],
  nascimento: null,
  programacao: [],
  biografia: ''
})
const confirmaSenha = ref('')

const senhaConfirmada = usuario.senha == confirmaSenha ? true : false
</script>

<template>
  <main>  
    <div class="form">
      <form class="form-info" action="">
        <h1 class="titulo">Formulário</h1>
        <input class="input-user" v-model="usuario.nome" type="text" placeholder="Nome" required />
        <input class="input-user"  v-model= "usuario.email" type="email" placeholder="Email"  />
        <input class="input-user" v-model= "usuario.senha" type="password" placeholder="Senha"  />
        <input class="input-user" v-model= "confirmaSenha" type="password" placeholder="Confirma Senha"  />
        <select class="input-user"  v-model="usuario.estados" name="estados" id="estados">
          <option v-for="estado in estados" :key="estado.sigla" :value="estado.sigla">{{ estado.nome }}</option>
        </select>
        <input class="input-user"  v-model="usuario.cidade" type="text" placeholder="Cidade"  />
        <input class="input-user"  v-model="usuario.endereco" type="text" placeholder="Endereço"  />
        <label for="">hobbies</label>
        <div v-for="(hobbie, id) in hobbies" :key="id">
          <input type="checkbox" v-model="usuario.hobbies" :value="hobbie">{{ hobbie }}
        </div>
        <input class="input-user" v-model="usuario.nascimento" type="date" placeholder="Data de nascimento"  />
        <label for="">Linguagem de programação favorita</label>
      <input class="input-user" type="radio" value="JavaScript" />
      <input class="input-user" type="text" placeholder="Biografia" />
      <input class="input-button" type="submit" name="" id="" />
    </form>
  </div>
  
  <div class="resultado">
    <h1>Resultado</h1>
    <div class="conteudo" >  
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
