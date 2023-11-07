<template>
     
    <sidebar/>
    
</template>

<script>
import { defineComponent } from 'vue';
import sidebar from '../components/sidebar.vue'

export default defineComponent({
 components:{
  sidebar,
  
  
  
 },
 
created(){
  console.log(sidebar);
  
  
}
});
</script>