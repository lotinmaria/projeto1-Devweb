<script setup>
import { reactive, ref } from 'vue'; 

const estados = [
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
]

const hobbies = [
  'caminhar',
  'ler',
  'nadar',
  'correr',
  'programar',
  'dançar',
  'pintar',
  'ouvir música',
]

const linguagens = [
  'java',
  'python',
  'php',
  'c++'
]

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

const mostrarResultado = ref(false)

function enviar(e) {
  if (confirmaSenha.value === usuario.senha) {
    mostrarResultado.value = true
    e.preventDefault()
  }
  else {
    alert('as senhas precisam ser iguais')
    e.preventDefault()
  }
  console.log("rodando")
}
</script>

<template>
  <main>  
    <div class="form" v-if="mostrarResultado == false">
      <form class="form-info" @submit="enviar">
        <h1 class="titulo">Formulário</h1>
        <input class="input-user" v-model="usuario.nome" type="text" placeholder="Nome" required/>
        <input class="input-user"  v-model="usuario.email" type="email" placeholder="Email" required />
        <input class="input-user" v-model="usuario.senha" type="password" placeholder="Senha" required />
        <input class="input-user" v-model="confirmaSenha" type="password" placeholder="Confirma Senha"  />
        <select class="input-user"  v-model="usuario.estado" name="estados" id="estados" required>
          <option v-for="estado in estados" :key="estado.sigla" :value="estado.sigla">{{ estado.nome }}</option>
        </select>
        <input class="input-user"  v-model="usuario.cidade" type="text" placeholder="Cidade"  />
        <input class="input-user"  v-model="usuario.endereco" type="text" placeholder="Endereço"  />
        <label class="titulo-input" for="">hobbies</label>
        <div class="checkbox-list">
        <div v-for="(hobbie, id) in hobbies" :key="id" class="checkbox-box">
          <input type="checkbox" v-model="usuario.hobbies" :value="hobbie" :name="hobbie"><label>{{ hobbie }}</label>
        </div>
      </div>
        <input class="input-user" v-model="usuario.nascimento" type="date" placeholder="Data de nascimento"  />
        <label class="titulo-input" for="">Linguagem de programação favorita</label>
        <div class="checkbox-list">
        <div v-for="(linguagem, id) in linguagens" :key="id" class="checkbox-box">
          <input type="checkbox" v-model="usuario.programacao" :value="linguagem"><label>{{ linguagem }}</label>
        </div>
      </div>  
      <label class="titulo-input" :for="usuario.biografia">Digite uma breve biografia:</label>
      <textarea v-model="usuario.biografia" cols="30" rows="5"></textarea>
      <input class="input-button" value="Enviar" type="submit">
    </form>
  </div>
  
  <div class="resultado" v-else>
    <h1>Resultado</h1>
    <div class="conteudo" >  
      <div class="infos">
        <h3>nome</h3>
        <p>{{ usuario.nome }}</p>
        <h3>email</h3>
        <p>{{ usuario.email }}</p>
        <h3>estado</h3>
        <p>{{ usuario.estado }}</p>
        <h3>cidade</h3>
        <p>{{ usuario.cidade }}</p>
        <h3>endereco</h3>
        <p>{{ usuario.endereco }}</p>
        <h3>data de nascimento</h3>
        <p>{{ usuario.nascimento }}</p>
        <h3>hobbies</h3>
        <p v-for="(hobbie, id) in usuario.hobbies" :key="id">{{ hobbie }};</p>
        <h3>linguagens de programação</h3>
        <p v-for="(linguagem, id) in usuario.programacao" :key="id">{{ linguagem }};</p>
        <h3>biografia</h3>
        <p>{{ usuario.biografia }}</p>
      </div>
      <button @click="mostrarResultado = false" class="input-button">editar</button>
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
  width: 30vw;
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
  margin: 5%;
}
.resultado{
  background-color: rgb(107, 158, 141);
  width: 20vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 3px solid black;
  border-radius: 10px;
  padding: 1% 2%;
  gap: 8px;
}

.checkbox-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: 15%;
}

.checkbox-box {
  width: 35%;
}


.titulo-input {
  font-weight: bold;
}
</style>