<template>
  <div id="app">
    <PdfViewer :fileUrl="fileUrl"/>
  </div>
</template>

<script>
import PdfViewer from './components/PdfViewer.vue';
export default {
  name: 'App',
  components: {
    PdfViewer
  },
  data() {
    return {
      fileUrl: 'compressed.tracemonkey-pldi-09.pdf'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
