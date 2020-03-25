<template>

    <div class="root">
        <button @click='clickedCount' class='btn btn-sm btn-outline-secondary'> This button has been clicked {{ counter }} times </button>
    </div>

</template>

<script>
export default {
    name: 'myButton',
    data (){
        return{
            counter: 0,
        }
    },
    methods:{
        clickedCount:function(){
            this.counter++;
        }
    }
}
</script>

<style>
    @import '../../node_modules/bootstrap/dist/css/bootstrap.min.css';
</style>