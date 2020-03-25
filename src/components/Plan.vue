<template>
    <div @click='seleccionar' class="plan" :class='{seleccionado : seleccionado}'>
        <div class="descripcion">
          <span class="titulo">
              {{ titulo }}
          </span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'plan',
    /* props: ['titulo'] Defining Prop as an array */
    /* But we can as well definde them as objects, just like... */
    props: {
        titulo: {
            type: String,
            default: 'Plan por defecto',
            required: true
        },
        precio: Number,
        cantidadSeleccionada: Number
    },
    data(){
        return {
            seleccionado: false
        }
    },
    methods:{
        seleccionar:function(){
            if(this.cantidadSeleccionada === 1 && !this.seleccionado){
                alert('Ya ha seleccionado otro plan');
            }
            /* Execute ONLY if it has NO plan selected Yet */
            if(this.cantidadSeleccionada === 0){
                this.seleccionado = true;
                /* Custom events */
                /* This one is in order to know which one was selected */
                this.$emit('seleccion', this.titulo);
                /* This one is in order to let the parent (planes) know it has already one child selected */
                this.$emit('alreadySelect', 1);
            }
            /* Allowing you to unselect it, only if this one was the one selected */
            if(this.cantidadSeleccionada === 1 && this.seleccionado){
                this.seleccionado = !this.seleccionado;
                /* Custom event to tell parent (planes) it doesn't have a selected child anymore */

                this.$emit('alreadySelect', 0);
            }


        },

    }

}
</script>

<style>

    .plan{
    margin:10px;
    background-color:azure;
    width:40%;
    min-width:300px;
    max-width: 600px;
    padding:10px;
    border-radius: 2px;
    cursor:pointer;
    transition: ease .3s;
    }
    .plan:hover{
    box-shadow: 0 10px 20px 0 rgba(95, 6, 6, 0.11), 0 5px 15px 0 rgba(61, 4, 4, 0.08);
    background-color:coral;
    color:white;
    }
    .seleccionado{
        background-color:rgb(243, 151, 118);
        border-color: #df0d4c
    }
    .descripcion{
        display:flex;
        justify-content: center;
    }

</style>