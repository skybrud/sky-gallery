<script>
export default {
	props: {
		items: {
			type: Array,
			required: true,
		},
		lightbox: {
			type: [String, Boolean],
			default: false,
		},
	},
	computed: {
		lightboxId() {
			return typeof lightbox === 'string'
				? this.lightbox
				: Math.random().toString(35).substr(2, 5);
		},
	},
	methods: {
		openLightbox(index) {
			if (this.lightbox) {
				// index determines which slide to start on in lightbox
				this.$store.commit('SkyLightbox/TOGGLE', {
					name: this.lightboxId,
					activeIndex: index,
				});
			}
		},
	},
};
</script>

<template src="./SkyGallery.html"></template>
<style src="./SkyGallery.scss" scoped></style>
