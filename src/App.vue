<template>
  <div class="container mt-5">
    <SearchBar @termSearch="searchedTerm"></SearchBar>
    <VideoList :videos="inComingVideos"></VideoList>
    {{inComingVideos}}
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
const API_KEY = "AIzaSyCKRBKFcTuINkvWAIG-pD2QGtYVz7MGLmo";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
  },
  data() {
    return {
      inComingVideos: [],
    };
  },
  methods: {
    searchedTerm(fa) {
      console.log(fa);
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: fa,
          },
        })
        .then((response) => {
          this.inComingVideos = response.data.items;
        })
        .catch((err) => console.log(err.response));
    },
    resolve() {
      console.log(this.inComingVideos);
    },
  },
  computed: {},
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,400;0,900;1,400&display=swap");

body {
  background-color: #647591;
  font-family: "Montserrat", sans-serif;
}

.container {
  background-color: #1a1927;
  /* height: 600px; */
  padding: 20px;
  border-radius: 8px;
  -webkit-box-shadow: 3px 10px 54px -12px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 3px 10px 54px -12px rgba(0, 0, 0, 0.75);
  box-shadow: 3px 10px 54px -12px rgba(0, 0, 0, 0.75);
}
</style>