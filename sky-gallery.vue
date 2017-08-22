<script>
import SkyCrop from 'sky-crop';
import SkyLightbox from 'sky-lightbox';

export default {
	components: {
		SkyCrop,
		SkyLightbox,
	},
	props: {
		items: {
			type: Array,
			required: true,
		},
		lightbox: {
			type: String,
		},
	},
	methods: {
		openLightbox(index) {
			// index determines which slide to start on in lightbox
			this.$store.commit('skyLightbox/toggle', {
				name: this.lightbox,
				activeIndex: index,
			});
		},
	},
};
</script>

<template src="./sky-gallery.html"></template>
<style src="./sky-gallery.scss"></style>
