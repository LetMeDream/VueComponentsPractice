<template>

    <div class="planes">

      <plan v-for='(plan, i) in planes' :key = 'i' :titulo='plan.plan' :precio='plan.precio' :cantidadSeleccionada='cantidadSeleccionada' 
      @seleccion='planElegido' 
      @alreadySelect='alreadySelected'
      />

    </div>

</template>

<script>
import Plan from './Plan'

export default {
    name: 'Planes',
    components:{
        Plan
    },
    data(){
        return{
            planes:[
                {plan:'Plan 1 - Principiante' , precio:100},
                {plan:'Plan 2 - Intermedio' , precio:200},
                {plan:'Plan 3 - Avanzado' , precio:300},
                {plan:'Plan 4 - Hacker' , precio:400},
                {plan:'Centrado' , precio:50}
            ],
            planSeleccionado: null,
            cantidadSeleccionada: 0
        }
    },
    methods:{
        planElegido(plan){
            this.planSeleccionado = plan;
        },
        alreadySelected(number){
            this.cantidadSeleccionada=number;
        }
    }
}
</script>

<style>

    .planes{
    width:700px;
    justify-content: center;
    display:flex;
    flex-direction: row;
    flex-wrap: wrap;
    position:relative;
    left:50%;
    transform: translateX(-50%);
    }
    @media screen and (max-width:680px){
    .planes{
        width:100%;
        flex-direction: column;
        align-items: center;
    }

    }

</style>