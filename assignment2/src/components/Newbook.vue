<template>
    <div class="container">
        <div class="row">
            <div class="column">                
                <p v-if="bookinformation !== null">Recently Added Book : {{ `${bookinformation.bookname}, ${bookinformation.published}, \$${bookinformation.price}`}}</p>
            </div>
        </div>        
    </div>
</template>
<script>
export default {
    name: 'Newbook',
    props: {
        bookdata: Object
    },
    data () {
        return {
            bookinformation : this.bookdata
        }
    },
    watch: {
        bookdata: function(newbookdata) {
            this.bookinformation = newbookdata;
        }
    }

}
</script>
<style scoped>
    p {
        font-size: 2.1em;
        color: #e83e8c;
    }
</style>>