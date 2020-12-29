<template>
	<div class="column" v-bind:style="{flex: `${flexProp}`}">
	<div class="item-box">
		<a href="#" class="border" v-bind:style="{border: `${border.width} ${border.type} ${border.color}`}">
			<div class="item-box__image">
				<div class="item-box__top">
					<div class="item-box__icon">
						<img src="@/assets/images/heart.png" alt="">
					</div>
					<div class="item-box__name">
						<div class="item-box__title">Медицина 24/7</div>
						<div class="item-box__subtitle">2 ч. назад</div>
					</div>
				</div>
				<img v-bind:src="require(`@/assets/images/${this.column.id}.jpg`)" alt="" v-bind:style="{padding: `${picture.padding}`}">
			</div>

			<div class="item-box__text" v-bind:style="{margin: `${text.margin}`}">
				<div class="item-box__descr" v-bind:style="{color: `${text.color}`, 'font-size': `${text.size}`, padding: `${text.padding}`, margin: `${text.margin}`}">
					{{ column.title }}
					<span class="item-box__else">Ещё</span>
				</div>
				<div class="item-box__socials">
					<div class="item-box__social item-box__likes">205</div>
					<div class="item-box__social item-box__comments">33</div>
					<div class="item-box__social item-box__refs">117</div>
				</div>
				<div class="item-box__bottom">
					<div class="item-box__date"><span>3</span> ч. назад</div>
					<div class="item-box__menu"></div>
				</div>
				<div class="item-box__btn">Читать далее</div>
			</div>

			<div class="item-box__shadow"></div>
		</a>
	</div>
	</div>
</template>

<script>
import Large from '@/components/Large'
// import Carousel from '@/components/Carousel'
import Graphical_4 from '@/components/Graphical_4'
// import Horizontal_1 from '@/components/Horizontal_1'
// import Horizontal_4 from '@/components/Horizontal_4'
import Horizontal_5 from '@/components/Horizontal_5'
import Horizontal_6 from '@/components/Horizontal_6'
import Social from '@/components/Social'
// import Smart_1 from '@/components/Smart_1'
import With_date from '@/components/With_date'

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
</style>