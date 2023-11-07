<template>
     <topbar/>
    <sidebar/>
    
</template>

<script>
import { defineComponent } from 'vue';
import sidebar from '../components/sidebar.vue'
import topbar from '../components/topbar.vue'
export default defineComponent({
 components:{
  sidebar,
  topbar,
  
 },
 
created(){
  console.log(sidebar);
  console.log(topbar);
  
}
});
</script>