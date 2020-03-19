<template>
    <q-form >  
        <q-input
        v-if="tab == 'registro'" 
        outlined 
        v-model="formData.name" 
        class="q-mb-md"
        label="Nombre"/>
        <q-input 
        outlined 
        v-model="formData.email"
        class="q-mb-md" 
        label="E-mail"/>
        <q-input 
        outlined 
        v-model="formData.password"
        class="q-mb-md" 
        label="Password"/>
        <div class="row">
            <q-btn 
            class="full-width" 
            color="primary"
            @click="submitForm" 
            :label="tab" 
            />
        </div>
    </q-form>
</template>
<script >
export default{
    props: ['tab'],
    data(){
        return{
            formData:{
                name: '',
                email:'',
                password:''
            }
        }
    },
    methods:{
        submitForm(){
            if(this.tab=='login'){
                console.log('Iniciar Sesion')
            }else{
                console.log('Registro')
            }
        }
    }
}

</script>