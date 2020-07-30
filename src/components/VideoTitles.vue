<template>
  <div class="list-item">
    <div class="box">
      <div class="left">
        <div class="thumbnail-box">
          <img :src="video.snippet.thumbnails.default.url" alt="thumbnail" />
        </div>
        <div>
          <p class="title" v-html="video.snippet.title.substring(0, 40) + '...'"></p>
          <p class="artist" v-text="video.snippet.channelTitle">Rihanna</p>
        </div>
      </div>
      <div class="right">
        <p class="time">03:42</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoTitles",
  props: ["video"],
  computed: {},
};
</script>

<style scoped>
.list-item {
  padding: 10px 10px 10px 10px;
}

.list-item:first-child {
  background-color: #252438;
  border-radius: 5px;
}
.left {
  display: flex;
}

.thumbnail-box {
  width: 55px;
  border-radius: 4px;
  margin-right: 10px;
  height: 43px;
}

.thumbnail-box img {
  width: 100%;
  height: 100%;
}

.title {
  margin-bottom: 4px;
  line-height: 1;
  font-weight: 500;
}

.artist {
  font-weight: 100;
  font-style: italic;
  font-size: 10px;
  margin-top: 0px;
  color: #bbb;
  margin-bottom: 0;
}

.time {
  font-size: 14px;
  font-style: italic;
  margin-bottom: 0;
}

.box {
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
</style>