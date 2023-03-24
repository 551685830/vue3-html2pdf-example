<template>
  <vue3-simple-html2pdf
    ref="vue3SimpleHtml2pdf"
    :options="pdfOptions"
    :filename="exportFilename"
  >
    <div class="main-content">
      <img alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
      <HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
      <HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
      <HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
    </div>
  </vue3-simple-html2pdf>

  <button @click="download">Download pdf</button>
</template>

<script>
import HelloWorldVue from "./components/HelloWorld.vue";
export default {
  name: "App",
  components: {
    HelloWorld: HelloWorldVue,
  },
  data() {
    return {
      pdfOptions: {
        margin: 15,
        image: {
          type: "jpeg",
          quality: 1,
        },
        html2canvas: { scale: 3 },
        jsPDF: {
          unit: "mm",
          format: "a4",
          orientation: "p",
        },
      },
      exportFilename: "my-custom-file.pdf",
    };
  },
  methods: {
    download() {
      this.$refs.vue3SimpleHtml2pdf.download();
    },
  },
};
</script>

<style>
#app,
.main-content {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
