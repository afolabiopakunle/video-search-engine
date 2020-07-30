<template>
	<div class="row main-frame">
		<div class="col-md-8">
			<div class="embed-responsive embed-responsive-16by9">
				<iframe class="embed-responsive-item" :src="videoSRC" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
			</div>
			<p class="pt-2">Lorem Ipsum</p>
		</div>
		<div class="col-md-4">
			<VideoTitles v-for="video in videos" :video="video" :key="video.etag"></VideoTitles>
		</div>
	</div>
</template>

<script>
import VideoTitles from "./VideoTitles";
export default {
	name: "VideoList",
	components: {
		VideoTitles,
	},
	props: ["videos"],
	computed: {
		videoSRC() {
			// console.log(videos);
			return `https://www.youtube.com/embed/VjnTS7JphVE`;
		},
	},
};
</script>

<style scoped>
.main-frame {
	display: flex;
	margin-top: 5px;
	border-radius: 5px;
	background: transparent;
	color: white;
	/* min-height: 90%; */
}
</style>
