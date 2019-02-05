<template>
  <form @submit.prevent="createUrl">
    <input
      type="text"
      placeholder="Cole seu link aqui e pressione enter"
      v-model="shareUrl"
      class="form-control"
    >

    <ul>
      <li v-for="(url, index) in urls" :key="index">
        <a class="mr-2" :href="url.urlToImage" target="_blank">{{url.urlToImage}}</a>
        
        <button
          class="btn btn-primary"
          type="button"
          v-clipboard:copy="url.urlToImage"
        >Copiar</button>
      </li>
    </ul>
  </form>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      shareUrl: "",
      urls: []
    };
  },
  methods: {
    createUrl() {
      const urlToImage = this.shareUrl.replace(
        /(.*file\/d\/)(.*)(\/view.*)/,
        "https://drive.google.com/uc?export=view&id=$2"
      );
      this.urls.push({ shareUrl: this.shareUrl, urlToImage });
      this.shareUrl = "";
      this.$copyText(urlToImage);
    },
    successo() {
      
    }
  }
};
</script>
