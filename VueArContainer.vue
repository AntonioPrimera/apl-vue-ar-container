<template>
	<div style="position:relative;">
		<div :style="`position:relative;width:100%;padding-top:${arPercent}%;`">
			<div style="position:absolute;top:0;bottom:0;left:0;right:0;">
				<slot></slot>
			</div>
		</div>
	</div>
</template>

<script>
	/**
	 * Props:
	 * 	- ar (string, mandatory): the aspect ratio of the image to be displayed: width/height (e.g. 1/1, 4/3, 16/9 etc.)
	 */
	export default {
		props: {
			ar: String,
		},
		
		computed: {
			arPercent() {
				let dimensions = this.ar.split('/');
				let width = dimensions.length === 2 && dimensions[0] > 0 ? dimensions[0] : 1;
				let height = dimensions.length === 2 && dimensions[1] > 0 ? dimensions[1] : 1;
				
				return width / height * 100;
			}
		},
	}
</script>