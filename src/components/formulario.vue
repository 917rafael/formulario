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




const usuario = reactive({
  nome: '',
  Email: '',
  senha: '',
  confirmacao: '',
  data:'',
  endereco:'',  
  cidade:''
})



</script>

<template>

  <div class="container">
    <main>
      <div class="nome">
        <label for="Nome" class="form-label">Nome:</label>
        <input type="text" class="form-control" id="nome" v-model="usuario.nome" />
      </div>
      
      <div class="email">
        <label for="email" class="form-label">Email:</label>
        <input type="text" class="form-control" id="email" v-model="usuario.Email" />
      </div>
      
      <div class="senha">
        <label for="Senha" class="form-label">senha:</label>
        <input type="password" class="form-control" id="Senha" v-model="usuario.senha" />
      </div>
      
      <div class="confirmacao">
        <label for="confirmacao" class="form-label">Confirme a senha:</label>
        <input type="password" class="form-control" id="confirmacao" v-model="usuario.confirmacao" />
      </div>
      
      <div class="data">
        <label for="data" class="form-label">Data de nascimento:</label>
        <input type="date" class="form-control" id="data" v-model="usuario.data" />
      </div>
      
      <div class="endereco">
        <label for="endereco" class="form-label">Endereço:</label>
        <input type="text" class="form-control" id="endereco" v-model="usuario.endereco" />
      </div>
        
      <div class="cida">
        <label for="cicade" class="form-label">Cidade:</label>
        <input type="text" class="form-control" id="cidade" v-model="usuario.cidade" />
      </div>

    
    </main> 
    <button @click="salvar">Salvar</button>
  </div>
 

</template>

<style scoped>



.form-label{
  display: flex;

}
.container {
    color: rgb(255, 255, 255);
    background-color: blue;
    border-radius: 6px;
    height: 450px;
    width: 450px;
    border-color: black;
}

.nome{
    background-color: black;
    margin-top: 15px;
    margin-left: 15px;
    width: 300px;
    border-radius: 15px;
}
.email {
    background-color: black;
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
