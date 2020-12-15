<template>
  <div class="column" v-bind:style="{flex: `${flexProp}`}">
	<div class="border" v-bind:style="{border: `${border.width} ${border.type} ${border.color}`}">
		<div class="image">
			<img src="@/assets/01.jpg" alt="" v-bind:style="{padding: `${picture.padding}`}">
		</div>
		<div class="text" v-bind:style="{color: `${text.color}`, 'font-size': `${text.size}`, padding: `${text.padding}`}">
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Error praesentium asperiores totam. Laborum quis unde perferendis qui labore!
		</div>
	</div>
  </div>
</template>

<script>
export default {
	props: {
		valueColumns: Number,
		column: Object,
		border: Object,
		text: Object,
		picture: Object
	},
	computed: {
		flexProp() {
			if (this.valueColumns == 1) {
				return '1 1 100%'
			}
			if (this.valueColumns == 2) {
				return '0 1 50%'
			}
			if (this.valueColumns == 3) {
				return '0 1 33.333%'
			}
			if (this.valueColumns == 4) {
				return '0 1 25%'
			}
			if (this.valueColumns == 5) {
				return  '0 1 20%'
			}
		}
	}
}
</script>

<style lang="scss" scoped>
.column {
	padding: 0 10px;
	margin: 0px 0px 20px 0px;
}
.image {
	position: relative;
	height: 300px;
	min-width: 200px;
	
	img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		object-fit: cover;
	}
}
.text {
	line-height: 1.2;
}
</style>