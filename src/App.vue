<template>
  <div class="container">
    <h1 class="text-center">{{header}}   </h1>
  <div class="small text-center text-muted">{{alert}}</div>
    <hr />
    <div class="row">
      <appImage @image-section="Image=$event"></appImage>
      <appCreateProduct  :image="Image" @product-section="Product=$event"></appCreateProduct>
    </div>
      <br />
      <br />
      <div class="progress">
        <div
          class="progress-bar bg-info"
          role="progressbar"
          :style="{width: (this.Product.length*10)+'%'}"
          aria-valuenow="50"
          aria-valuemin="0"
          aria-valuemax="100"
        >{{Product.length}}/10</div>
      </div>

    <br />
    <br />
    <h3 class="text-center">{{getAllHeader}}</h3>
    <hr />
    <appgetAll :image="Image" :products="Product"></appgetAll>
  </div>
</template>

<script>
import Image from "./components/Image";
import CreateProduct from "./components/CreateProduct";
import getAll from "./components/getAll";
export default {
  components: {
    appImage: Image,
    appCreateProduct: CreateProduct,
    appgetAll: getAll
  },
  data() {
    return {
      getAllHeader: "Eklenen Ürünlerin Listesi",
      header: "Ürün Ekleme Uygulaması",
      alert:"*10 Adet ürün Ekleyebilirsiniz!",
      Product: [],
      Image:[]
    };
  }
};
</script>

<style>
body {
  background-color: aliceblue;
  padding-top: 20px;
  padding-bottom: 20px;
}

.card {
  margin-right: 5px;
  margin-bottom: 5px;
}

.card:last-child {
  margin-right: 0px;
}

.col-md-2 {
  max-width: 15.666667% !important;
}

.product-container {
  margin-left: 15px;
}
</style>

