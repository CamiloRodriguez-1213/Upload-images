<template>
  <div class="container" style="height: 35rem; background-color:white">
    
    <div class="row py-5">
      
      <div class="col-12 py-5">
        
        <div class="card tarjeta">
          <h1 class="text-center">Subir archivo</h1>
          <div class="card-footer">
            
              <input  style="display: 150px;" class="carga py-5 pl-5" type="file" @change="onFileSelected($event)">
              <br><br>
            
            <div class="row justify-content-center">
        <button type="submit" @click="onUpload" style="width:15rem" class="btn btn-primary">Subir imagen</button>
      
    </div>
          </div>
        </div>
      </div>
    </div>
    
    
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Home',
    data(){
      return{
        selectedFile: null,
      }
    },
    methods: {
      onFileSelected(event){
        this.selectedFile = event.target.files[0]
      },
      onUpload(){
        const fd = new FormData();
        fd.append('url', this.selectedFile,this.selectedFile.name)
        axios.post("https://api.jeisontech.dev/api/images/",fd)
        .then(res => {
          console.log(res)
        })
      }
}
};

</script>

<style>
.tarjeta{
  width: 50rem;
  height: 12rem ;
  border: none;
}
.card-footer{
  text-align: center;
  background-color: white;
  border: none;
  
}
.carga{
  
  height: 150px;
  width: 100%;
  background-color: white;
  border: 1px solid rgb(0, 0, 0);
  
  
}


</style>