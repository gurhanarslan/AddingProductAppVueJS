<template>
 
    
    <div class="col-md-5">
      <div class="col-md-11 card">
        <div class="card-body">
          <div class="form-group">
            <label>Ürün Adı</label>
            <input
              type="text"
              v-model="ProductName"
              class="form-control"
              placeholder="adını giriniz"
            />
          </div>
          <div class="row">
            <div class="form-group col-md-6">
              <label>Ürün Adeti</label>
              <input
                type="number"
                v-model="ProductNumber"
                class="form-control"
                placeholder="adetini giriniz"
              />
            </div>
            <div class="form-group col-md-6">
              <label>Ürün Fiyatı</label>
              <input
                type="number"
                v-model="ProductPrice"
                class="form-control"
                placeholder="fiyatını giriniz"
              />
            </div>
          </div>
          <button @click="create" class="btn btn-outline-info btn-block">Ekle!</button>
        </div>
      </div>
    </div>
 
</template>
<script>
export default {
  data() {
    return {
      Product: [],
      ProductName: "",
      ProductPrice: 0,
      ProductNumber: 0,
      TotalProduct: 0,
      
    };
  },
  props:["image"],
  methods: {
    create() {
        if(this.Product.length<10){
                  var name = this.ProductName;
      var price = this.ProductPrice;
      var number = this.ProductNumber;
        var img = this.image
      this.Product.push({
        ProductName: name,
        ProductPrice: price,
        ProductNumber: number,
        ProductImage: img
      });
      console.log()
      this.$emit("product-section", this.Product);
      this.ProductName = "";
      (this.ProductPrice = 0), (this.ProductNumber = 0);
        }
        else{
            alert("Daha Fazla Ürün Ekleyemezsiniz!")
        }
    
    
    },
   
  }
};
</script>