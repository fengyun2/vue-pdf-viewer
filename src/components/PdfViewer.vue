<template>
  <div class="container">
    <iframe :src="pdfurl" width="100%" height="100%"></iframe>
  </div>
</template>

<script>
  export default {
    name: "PdfViewer",
    props: {
      fileUrl: {
        type: String,
        default: "http://storage.xuetangx.com/public_assets/xuetangx/PDF/PlayerAPI_v1.0.6.pdf",
      },
    },
    data() {
      return {
        pdfurl: "",
      };
    },
    mounted() {
      // const {id} = this.$route.query
      // 获取预览文件的完整接口地址，根据具体情况编写，反正path就是一个预览文件的接口地址
      // const path = this.$api.filePreview(id)
      // let path = 'http://14.1.1.1:8088//file/downloadFile?id=140'
      // let path = '/腾讯文档高效质量交付(吴涛)20-3.pdf'
      // let path =
        // "http://storage.xuetangx.com/public_assets/xuetangx/PDF/PlayerAPI_v1.0.6.pdf";


      const viewerUrl = "/pdfjs3/web/viewer.html";
      const path = this.fileUrl
      // 生产环境下
      if (process.env.NODE_ENV === "production") {
        this.pdfurl = viewerUrl + "?file=" + encodeURIComponent(path);
      } else {
        // 开发环境
        this.pdfurl = viewerUrl + "?file=" + encodeURIComponent(path);
      }
    },
  };
</script>

<style scoped lang="scss">
  .container {
    height: 100vh;
  }
</style>
