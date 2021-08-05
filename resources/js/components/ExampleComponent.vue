<template>
    <div class="container mt-5">
        <div class="row justify-content-center" style="text-align:center;">
            <div class="col-4">
                <form class="was-validated">
                    <input type="text" class="form-control is-invalid" v-model="texto" placeholder="Ingresa el texto aquí" pattern="[a-zA-Z ]{2,254}" required>
                </form>
            </div>
            <div class="col-4">
                <button type="button" class="btn btn-outline-primary" v-on:click="invertir">Invertir texto</button>
            </div>
            <div class="col-4">
                <p v-if="texto==''">No hay nada escrito aún</p>
                <p v-else>{{txt}}</p>
            </div> 
        </div>                 
    </div>
</template>

<script>
export default{
    data: function(){
        return{
            texto:'',
            txt:''
        }
    },
    methods:{
        invertir: function (event){
            if(this.texto.match(/^[0-9]+$/)){
                alert('solo se permiten letras!');
                return this.texto='';
            }
            else if(this.texto=='') {
                return this.txt='No hay nada escrito aún';
            }
            else{
                return this.txt='Resultado:  '+ this.texto.split('').reverse().join('');
            }
        }
    }
}
</script>