<template>
	<div></div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
* {
	padding: 0px;
	margin: 0px;
	border: 0px;
}
.horizontal_4 {
	.container {
	padding: 30px 10px;
	margin: 10px auto;
	}

	.arrow {
	display: none;
	}

	.row {
	border: 1px dashed #1E6BD1;
	}

	.item-box {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	padding: 10px;
	margin: 0px 0px 8px 0px;
	}

	@media (max-width: 767.98px) {
	.item-box {
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
			-ms-flex-direction: column;
				flex-direction: column;
		padding: 10px 10px 20px;
	}
	}

	.item-box__image {
	-webkit-box-flex: 0;
		-ms-flex: 0 0 492px;
			flex: 0 0 492px;
	position: relative;
	padding: 0px 0px 31.6% 0px;
	}

	.item-box__image img {
	position: absolute;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	-o-object-fit: cover;
		object-fit: cover;
	}

	@media (max-width: 1024px) {
	.item-box__image {
		-webkit-box-flex: 0;
			-ms-flex: 0 1 50%;
				flex: 0 1 50%;
	}
	}

	@media (max-width: 767.98px) {
	.item-box__image {
		margin: 0px 0px 20px 0px;
		padding: 0px 0px 50% 0px;
	}
	}

	.item-box__text {
	padding: 0 20px;
	font-size: 25px;
	text-align: left;
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-webkit-box-orient: vertical;
	-webkit-box-direction: normal;
		-ms-flex-direction: column;
			flex-direction: column;
	}

	@media (max-width: 1024px) {
	.item-box__text {
		-webkit-box-flex: 0;
			-ms-flex: 0 1 50%;
				flex: 0 1 50%;
	}
	}

	@media (max-width: 767.98px) {
	.item-box__text {
		padding: 0;
	}
	}

	.item-box__descr {
	-webkit-box-flex: 1;
		-ms-flex: 1 1 100%;
			flex: 1 1 100%;
	margin: 0px 0px 20px 0px;
	color: #124f96;
	}

	.item-box__descr:hover {
	text-decoration: underline;
	}

	.item-box__btn {
	margin-left: auto;
	padding: 12px 30px;
	color: #0a0ab2;
	font-size: 20px;
	font-weight: 500;
	border-radius: 3px;
	font-weight: 600;
	font-style: oblique;
	text-decoration: underline;
	}

	.item-box__shadow {
	display: none;
	}

	.item-box__else {
	display: none;
	}

	.item-box__socials {
	display: none;
	}

	.item-box__top {
	display: none;
	}

	.item-box__title {
	display: none;
	}

	.item-box__subtitle {
	display: none;
	}

	.item-box__bottom {
	display: none;
	}

	.item-box__date {
	display: none;
	}

	.item-box__menu {
	display: none;
	}

	.item-box__icon {
	display: none;
	}

	.item-box__likes {
	display: none;
	}

	.item-box__comments {
	display: none;
	}

	.item-box__refs {
	display: none;
	}
}
</style>