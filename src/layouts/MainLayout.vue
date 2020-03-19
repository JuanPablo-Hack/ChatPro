<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        
        <q-btn 
         v-if="$route.fullPath.includes('/chat')"
         v-go-back.single
         color="white" 
         icon="arrow_back" 
         flat  
         dense/>
        <q-toolbar-title class="absolute-center">
         {{title}}
        </q-toolbar-title>
        <q-btn
         to="/auth" 
         class="absolute-right q-pr-sm"
         no-caps
         color="white" 
         icon="account_circle" 
         flat  
         dense/>
        
      </q-toolbar>
    </q-header>

    

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import {openURL} from 'quasar'

export default {
  computed:{
    title(){
      let currentPath= this.$route.fullPath
      if(currentPath=='/')return 'ChatPro'
      else if(currentPath=='/chat') return 'Chat'
      else if(currentPath=='/auth') return 'Perfil'
    }
  }
}
</script>
