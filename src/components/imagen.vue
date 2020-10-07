<template>
    <div class="card">
          <img class="img-fluid" :src="imagen.url" alt="">
          <div class="card-body">
            <h5 class="card-title"><p>{{imagen.created_at}}</p></h5>
          </div>
        </div>
</template>
<script>
export default {
    name: "Imagen",
    props: ["imagen"]
}
</script>
<style>

</style>