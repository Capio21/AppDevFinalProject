<template>
     <div id = "wrapper">
       
        <sidebar/>
     <topbar/>
     
   
     </div>
    
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
<style>
@import '../assets/asset/admin/css/sb-admin-2.css';
@import '../assets/asset/admin/css/sb-admin-2.min.css';

</style>
