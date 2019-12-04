<template>
    <div class="row product-container">
      <div class="col-md-2 card" v-for="(item) in (products)">
          <img height="128" class="img-responsive text-center mb-3"
               :src="item.ProductImage == null ? '/src/assets/default.png' : item.ProductImage">
        <div class="card-body">
          <h5 class="card-title">{{item.ProductName}}</h5>
          <small>
            <strong>Adet : </strong> {{item.ProductNumber}} 
          </small>
          <br>
          <small>
            <strong>Fiyat : </strong> {{item.ProductPrice}}
          </small>
          <br>
          <small>
            <strong>Tutar : </strong> {{(item.ProductNumber)*(item.ProductPrice)}}
          </small>
        </div>
      </div>


    </div>
</template>
<script>
export default {
    data(){
        return{
        
        }
        
    },
    props:["products","image"],
  
    
  
    
    
}
</script>