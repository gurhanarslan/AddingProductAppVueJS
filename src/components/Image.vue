<template>
    <div class="card offset-2 col-md-3">
      <div class="card-body tex-center d-flex align-items-center flex-column">
        <img
          height="128"
          class="img-responsive text-center mb-3"
          :src="product.ProductImage == null ? '/src/assets/default.png' :product.ProductImage"
        />
        <input
          ref="file"
          type="file"
          style="display: none;"
          @change="onChange($event)"
          class="form-control"
        />
        <button
          class="btn btn-outline-secondary"
          type="button"
          @click="$refs.file.click()"
        >Resim Seç</button>
      </div>
    </div>
</template>

<script>
export default {
     data() {
      return {
     imageList: [],
      product: {
        ProductImage: null
      }
      }
    },
    methods:{
   
       onChange(e) {
      const file = e.target.files[0];
      this.product.ProductImage = URL.createObjectURL(file);
      console.log(file);
      var image = URL.createObjectURL(file);
      this.$emit("image-section",image)
    }
    }
    
}
</script>