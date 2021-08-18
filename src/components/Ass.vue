<template>
    <div class="container">
        <h2 class="text-center">Crie sua assinatura</h2>
        <div class="row">
            <div class="col-md-6">
                <h4>Preencha seus dados</h4>
                <input type="text" v-model="nome" class="form-control m-2" placeholder="Nome">
                <input type="text" v-model="departamento" class="form-control m-2" placeholder="Departamento">
                <input type="text" v-model="telefone" class="form-control m-2" placeholder="Telefone">
                <input type="email" v-model="email" class="form-control m-2" placeholder="E-nail">

                 <a href="#"  v-on:click="gerar" class="btn btn-primary btn-block m-2">Gerar</a>
            </div>
            <div class="col-md-6 ">
                <h4>Visualizar Assinatura</h4>
                <div id="assinatura" class="shadow-none p-3 mb-5 bg-light rounded">
                    <p> <strong> {{nome}} </strong>| Depto. {{departamento}}</p>
                    <p>{{telefone}}<br>
                    <strong>{{email}}</strong></p>
                </div>
               
            </div>
            <div class="col-md-6">
                 <Inserir />
            </div>
            <div class="col-md-6">
                   
                    <h4>Copie o código abaixo e cole na área de assinaturas do e-mails</h4>
                 <textarea
                    id="textarea"
                    v-model="text"
                    placeholder="Enter something..."
                    rows="3"
                    max-rows="6"
                   class="form-control" ></textarea>
            </div>
        </div>
    </div>
</template>
<script>
import Inserir from "./Inserir.vue"
export default {
    name: "Ass",
    components:{
        Inserir 
    },
    data(){
        return{
            nome: "",
            departamento: "",
            telefone: "",
            email:"",
            text:""
        }
    },
    methods:{
        gerar(){
           this.text = `<div id="assinatura" style="background-image: url(https://centraldaeconomia.com/wp-content/uploads/2021/08/assinaturas.jpg); background-repeat: no-repeat; background-size: 100%; width: 600px; height: 160px; text-align: center; font-size: 20px; padding-top: 2px; font-family: Rockwell;">
            <p> <strong>`+this.nome+`</strong>| Depto: `+this.departamento +`</p>
      <p>`+this.telefone+`<br>
      <strong>`+this.email+`</strong></p>
    </div>
           `

        }
    }
}
</script>
<style scoped>
#assinatura{
    background-image: url(https://centraldaeconomia.com/wp-content/uploads/2021/08/assinaturas.jpg);
    background-repeat: no-repeat;
    background-size: 100%;
    width: 600px;
    height: 160px;
    text-align: center;
    font-size: 20px;
    padding-top: 2px;
    font-family: Rockwell;
    
}
</style>