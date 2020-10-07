<template>
    <div class="container">
        <div class="row">
            <div class="column">
                <h1 :class="{'headercolor' : includeclass}" class="text-left">{{headerMessage}}</h1>
            </div>
        </div>        
    </div>    
</template>
<script>
export default {
    name: 'HeaderComp',
    props: {
        headertext: String,
        includeClass: Boolean
    },
    data () {
        return {
            headerMessage: this.headertext,
            includeclass: this.includeClass
        }
    }
}
</script>
<style scoped>
h1 {
    font-size: 2rem;    
}
.headercolor {
     font-size:2.5em;
     color: brown;
}
</style>