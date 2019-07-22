<template>
        <h1 class="list-item"
        v-on:click="removeItem"
        >{{ el }}</h1>
    
</template>

<script>
export default {
props : {
    el :String,
    id :Number
},
methods : {
    removeItem(){
        this.$emit('removeItem',this);
    }
}
}
</script>

<style lang='scss'>
.list-item{
    margin-bottom: 30px;
    box-shadow:0 1px 4px rgba(0, 0, 0, 0.3), 0 0 20px rgba(0, 0, 0, 0.1) ;
    padding-top: 10px;
    padding-bottom: 10px;
}

</style>
