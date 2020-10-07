<template>
    <div class="container mt-2" id="booktable">
        <div class="row" v-if="book.length">
            <div class="column">
                <h2 :style="{ color, fontSize}"> Books List - Technology</h2>
            </div>
        </div>
        <div class="row">
            <div class="column">
                <div v-if="book.length" class="table-responsive">
                    <table class="table table-striped table-hover">
                    <caption>List of Books</caption>
                    <thead class="thead-dark">
                        <tr>
                        <th scope="col">#</th>
                        <th scope="col">Title</th>
                        <th scope="col">Published. Year</th>
                        <th scope="col">Price</th>
                        </tr>
                    </thead>
                    <tbody class="">
                    <tr v-for="(item, index) in book" :key="item.index">
                    <td scope="row">{{++index}}</td>
                    <td>{{item.bookname}}</td>
                    <td>{{item.published}}</td>
                    <td>${{item.price}}</td>
                    </tr>
                    </tbody>
                    </table>
                </div>
                <div v-else>
                    <h2 class="nobook text-left p-2">No Books Available. Please add some Books</h2>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Book',
    props : {
        title : Object
    },
    data () {
        return {
            book : this.title.books,
            color: 'green',
            fontSize: '2em'
        }
    }    
}
</script>
<style scoped>
.nobook {
    font-size: 1.5em;
}
caption {
    caption-side: top;
}
table thead th {
    vertical-align: initial !important;
}
th {
    color: violet !important;
    font-size: 1.4em;
}
td {
    font-size: 1.4em;
}
</style>