<template>
  <q-page class="flex column">
    <q-banner class="bg-blue-2 text-white text-center">
      
      En linea
     
    </q-banner>
    <div class="q-pa-md column col justify-end">
       <div style="width: 100%; max-width: 400px">
      <q-chat-message
        
        v-for="message in messages"
        :key="message.text"
        :name="message.from"
        :text="[message.text]"
        :sent="message.from == 'Juan Pablo' ? true : false"
      />
    </div>
    </div>
     <q-footer>
       <q-toolbar>
          <q-form class="full-width">
              <q-input 
              bg-color="white" 
              class="full-width"  
              outlined rounded  
              v-model="newMessage"  
              dense>
                <template v-slot:after>
                  <q-btn 
                  round  
                  dense
                  flat  
                  @click="sendMessage"
                  color="white" 
                  icon="send"/>
                </template>
              </q-input>
          </q-form>    
       </q-toolbar>
     </q-footer>
  </q-page>
</template>

<script>
export default {
    data(){
      return{
        newMessage:'',
        messages:[
          {
            text:'Hola mi amor, buenos dias',
            from: 'Juan Pablo'
          },
          {
            text: 'Buenos dias precioso',
            from: 'Valeria Hermosa'
          },
          {
            text: 'Como amaneciste',
            from: 'Juan Pablo'
          }

        ]
      }
    },
    methods:{
      sendMessage(){
        
        this.messages.push({
          text: this.newMessage,
          from: 'Juan Pablo'
        })
        this.newMessage=''
      }
    }
}
</script>
