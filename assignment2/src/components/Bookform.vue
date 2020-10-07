<template>
  <div class="container mb-3">
    <div class="row">
      <div class="column column-12">
        <form class="form">
            <div class="form-group d-md-inline-block d-lg-inline-block d-sm-block mr-2">
                <label for="booktitle" class="mr-5">Enter Book Title</label>
                <input autocomplete="false" v-model.trim="bookname" type="text" class="form-control" id="booktitle" placeholder="Enter Book Title">
            </div>
            <div class="form-group d-md-inline-block d-lg-inline-block d-sm-block mr-2">
                <label for="bookyear" class="mr-1">Enter Publication Year</label>
                <input autocomplete="false" v-model.trim="bookyear" type="number" min="1000" max="9999" pattern="/^-?\d+\.?\d*$/" onKeyPress="if(this.value.length==4) return false;" class="form-control" id="bookyear" placeholder="Published Year" />
            </div>
            <div class="form-group d-md-inline-block d-lg-inline-block d-sm-block mr-2">
                <label for="price" class="mr-1">Enter Price</label>
                <input autocomplete="false" v-model.trim="price" type="number" min="1000" max="9999" pattern="/^-?\d+\.?\d*$/" onKeyPress="if(this.value.length==4) return false;" class="form-control" id="price" placeholder="Price" />
            </div>
            <button @click.prevent="addbook" class="btn btn-primary">Add Book</button>
        </form>        
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Bookform",
  data () {
    return {
      bookname: null,
      bookyear : null,
      price: null
    }
  },
  methods: {
    addbook() {
      if(this.bookname === null || this.bookyear === null || this.price === null) {
        alert('Please Enter all the details');
        return false;
      } else {
        this.$emit('addbook', [this.bookname, this.bookyear, this.price]);
        this.bookname = this.bookyear = this.price = '';
      }
    }
  }
};
</script>
<style scoped>
label {
  color: red;
}
</style>>