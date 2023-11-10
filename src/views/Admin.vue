<template>
    <div id="wrapper">
      <sidebar />
      <topbar />
      <tables />
      <charts />
    </div>
  </template>
  
  <script>
  import { onMounted } from 'vue';
  import { defineComponent } from 'vue';
  import sidebar from '../components/sidebar.vue';
  import topbar from '../components/topbar.vue';
  import tables from '../components/tables.vue';
  import charts from '../components/charts.vue';
  
  export default {
    name: 'Admin',
    components: {
      sidebar,
      topbar,
      tables,
      charts,
    },
  
    setup() {
      async function loadScript(src) {
        return new Promise((resolve, reject) => {
          const script = document.createElement('script');
          script.src = src;
          script.onload = resolve;
          script.onerror = reject;
          document.head.appendChild(script);
        });
      }
  
      async function loadScriptsInOrder(scriptUrls) { // Fixed the parameter name here
        for (const url of scriptUrls) { // Fixed the variable name here
          await loadScript(url);
        }
      }
  
      onMounted(async () => {
        await loadScriptsInOrder([
          '/scriptedJS/jquery.min.js',
          '/scriptedJS/bootstrap.bundle.min.js',
          '/scriptedJS/jquery.easing.min.js',
          '/scriptedJS/sb-admin-2.min.js',
          '/scriptedJS/Chart.min.js',
          '/scriptedJS/chart-area-demo.js',
          '/scriptedJS/chart-pie-demo.js',
        ]);
      });
    },
  };
  </script>
  
  <style>
  @import '../assets/asset/admin/css/sb-admin-2.css';
  @import '../assets/asset/admin/css/sb-admin-2.min.css';
  </style>
  