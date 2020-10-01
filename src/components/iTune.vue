
<template>
  <div class="container">
    <br/>
    <input type="text" v-model="keyword" />
    <button @click="searchData()">Search for artist name</button>
    <!--{{resultData}}-->

    <!--id = {{data.mal_id}}
      ชื่อ = {{data.title}}
      รายละเอียด = {{data.synopsis}}
      รูป = {{data.image_url}}-->     
    <b-card-group columns>
      <b-card
        v-for="data in resultData"
        :key="data.artistId"
        :title="data.trackName"
        :img-src="data.artworkUrl100"
        :sub-title="data.artistName"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem"
        class="mb-2"
      >
        <b-card-text>{{ data.synopsis }}</b-card-text>
        <audio controls="controls">
          <source :src="data.previewUrl" />
        </audio>
        <b-button :href="data.artistViewUrl" variant="primary"
          >Go somewhere</b-button
        >
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      resultData: null,
      keyword: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get("https://itunes.apple.com/search?term=" + this.keyword + "&page=1")
        .then((response) => {
          this.resultData = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
</style>