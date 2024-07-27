<!-- eslint-disable vue/multi-word-component-names -->
// eslint-disable-next-line vue/multi-word-component-names
<script setup>
import { reactive } from 'vue';
const emit = defineEmits(['adicinar'])

function salvar() {
  if (usuario.nome === '' || usuario.senha === '') {
    alert('Por favor preencha todos os campos!!!!!!!!!!!')
    return;
  } 
  else if (usuario.senha !== usuario.confirmacao){
    alert('Crendencias Inválidas')
  }
  else{
  emit('adicionar', { ...usuario})
  }
}

const estado = [{ // certo

nome: 'Acre',
sigla: 'AC'
}, {
nome: 'Alagoas',
sigla: 'AL'
},
{
nome: 'Macapá',
sigla: 'AP'
}, {
nome: 'Amazonas',
sigla: 'AM'
}
, {
nome: 'Bahia',
sigla: 'BA'
}
, {
nome: 'Ceará',
sigla: 'CE'
}
, {
nome: 'Distrito Federal',
sigla: 'DF'
},
{
nome: 'Espirito Santo',
sigla: 'ES'
},
{
nome: 'Goiáis',
sigla: 'GO'
},
{
nome: 'Maranhão',
sigla: 'MA'
},
{
nome: 'Mato Grosso',
sigla: 'MT'
},
{
nome: 'Mato Grosso do Sul',
sigla: 'MS'
},
{
nome: 'Minas Gerais',
sigla: 'MG'
},
{
nome: 'Pará',
sigla: 'PA'
},
{
nome: 'Paraíba',
sigla: 'PB'
},
{
nome: 'Paraná',
sigla: 'PR'
},
{
nome: 'Pernambuco',
sigla: 'PE'
},
{
nome: 'Piauí',
sigla: 'PI'
},
{
nome: 'Rio de Janeiro',
sigla: 'RJ'
},
{
nome: 'Rio Grande do Norte',
sigla: 'RN'
},
{
nome: 'Rio Grande do Sul',
sigla: 'RS'
},
{
nome: 'Rondônia',sigla: 'RO'},
{nome: 'Roraima',sigla: 'RR'},
{nome: 'Santa Catarina',sigla: 'SC'},
{nome: 'Tocantis',sigla: 'TO'},
{nome: 'São Paulo',sigla: 'SP'}];




const usuario = reactive({
  nome: '',
  Email: '',
  senha: '',
  confirmacao: '',
  data:'',
  endereco:'',  
  cidade:'',
  biografia:'',
  sigla:''
})



</script>

<template>

  <div class="container">
    <main class="main">
      <h1 class="h2">Formulario</h1>

      <div class="nome">
        <label for="Nome" class="form-label">Nome:</label>
        <input type="text" class="form-control" id="nome" v-model="usuario.nome" placeholder="Digite sue nome" />
      </div>
      
      <div class="email">
        <label for="email" class="form-label">Email:</label>
        <input type="text" class="form-control" id="email" v-model="usuario.Email" placeholder="Digite seu email " />
      </div>
      
      <div class="senha">
        <label for="Senha" class="form-label">senha:</label>
        <input type="password" class="form-control" id="Senha" v-model="usuario.senha" placeholder="Digite sua senha " />
      </div>
      
      <div class="confirmacao">
        <label for="confirmacao" class="form-label">Confirme a senha:</label>
        <input type="password" class="form-control" id="confirmacao" v-model="usuario.confirmacao" placeholder="confirme sua senha"  />
      </div>
      
      <div class="data">
        <label for="data" class="form-label">Data de nascimento:</label>
        <input type="date" class="form-control" id="data" v-model="usuario.data" />
      </div>
      
      <div class="endereco">
        <label for="endereco" class="form-label">Endereço:</label>
        <input type="text" class="form-control" id="endereco" v-model="usuario.endereco" placeholder="Digite sue endereço " />
      </div>
        
      <div class="cida">
        <label for="cicade" class="form-label">Cidade:</label>
        <input type="text" class="form-control" id="cidade" v-model="usuario.cidade" placeholder="Digite sua cidade " />
      </div>

      <div class="estados">
        <label for="">Estado:</label>
        <select name="estado" id="estado" class="form-control" v-model.lazy="usuario.sigla">
          <option v-for="(item, index) in estado" :value="item.sigla" :key="index.sigla"> {{ item.nome }} ({{ item.sigla}})
          </option>
        </select>

      </div>

      <div class="bio">
        <label for="biografia">Biografia:</label>
        <input type="text" v-model="usuario.biografia" placeholder="Digite sua biografia " />
      </div>
    <button class="button" @click="salvar">Salvar</button>
    </main> 
    
  </div>
 

</template>

<style scoped>

.bio{
  margin-left: 15px;
  width: 7px;
  margin-top: 10px
}
.estados{
  margin-left: 15px;
  width: 7px;
  margin-top: 10px
}

.h2{
  color: black;
  margin-top: 20px;
  margin-left: 29%
}

.main{
  margin-left: 10px;
}

.button{
  margin-left: 24%;
  margin-top: 10px;
  padding: 8px 80px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  cursor: pointer;
  border-radius: 25px;
  font-size: 16px;
  transition: background-color 1s ease;
  border: solid 7px;
}



.form-label{
  display: flex;

}
.container {
    color: rgb(255, 255, 255);
    background-color: blue;
    border-radius: 6px;
    height: 710px;
    width: 450px;
    border: solid 7px ;
}

.nome{

    margin-top: 15px;
    margin-left: 15px;
    width: 300px;
    border-radius: 15px;
}
.email {
    margin-left: 15px;
    margin-top: 15px;
    width: 300px;
}
.senha {
    margin-left: 15px;
    margin-top: 15px;
}
.confirmacao{
    margin-left: 15px;
    margin-top: 15px

}
.data{
    margin-left: 15px;
    margin-top: 15px;
}

.cida{
    margin-left: 15px;
    margin-top: 15px;
}
.endereco{
    margin-left: 15px;
    margin-top: 15px;

}

</style>
