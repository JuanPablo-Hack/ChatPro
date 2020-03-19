<template>
  <q-page class="flex q-pa-md">
    <q-list class="full-width" separator >
      <q-item v-for="contact in contacts" to="/chat" :key="contact.id"   class="q-my-sm" clickable   v-ripple>
        <q-item-section avatar>
          <q-avatar color="primary" text-color="white">
            {{ contact.name.charAt(0) }}
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ contact.name }}</q-item-label>
          
        </q-item-section>

        <q-item-section side>
          <q-badge :color="contact.online ? 'ligth-green-5' : 'grey-4'">
            {{contact.online ? 'En linea' : 'Desconectado' }}
          </q-badge>
          <q-icon name="chat_bubble" color="green" />
        </q-item-section>
      </q-item>

      
    </q-list>
  </q-page>
</template>

<script>

const contacts = [ {
  id: 1,
  name: 'Valeria',
  online: true
}, {
  id: 2,
  name: 'Memo',
  online: true

}, {
  id: 3,
  name: 'Gus',
  online: false
  
}, {
  id: 4,
  name: 'Alex',
  online: true
 
 
} ]


export default {
  data () {
    return {
      contacts
      
    }
  }
}

</script>
