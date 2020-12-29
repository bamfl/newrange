<template>
	<div id="app">
		<div class="container">
			<label>
				Выберите шаблон:
				<select class="select graphical_4" v-model="blocksType" @change="addClass">
					<option value="large">Большой</option>
					<!-- <option value="carousel">Карусель</option> -->
					<option selected value="graphical_4">Графический 4</option>
					<!-- <option value="horizontal_1">Горизонтальный 1</option> -->
					<!-- <option value="horizontal_4">Горизонтальный 4</option> -->
					<option value="horizontal_5">Горизонтальный 5</option>
					<option value="horizontal_6">Горизонтальный 6</option>
					<option value="social">Социальный</option>
					<!-- <option value="smart_1">Smart 1</option> -->
					<option value="with_date">Объявление с датой публикации</option>
				</select>
			</label>
			<label><input type="range" min="1" max="5" step="1" v-model="valueColumns">Кол-во колонок: {{ valueColumns }}</label>
			<label><input type="range" min="1" max="3" step="1" v-model="valueRows">Кол-во рядов: {{ valueRows }}</label>
			<label><input type="text" v-model="border.width">Толщина рамки</label>
			<label><input type="color" v-model="border.color">Цвет рамки</label>
			<label>
				<select v-model="border.type">
					<option selected value="solid">Сплошная</option>
					<option value="dotted">Пунктирная</option>
					<option value="dashed">Штриховая</option>
					<option value="double">Двойная</option>
					<option value="groove">Вдавленная</option>
					<option value="ridge">Рельефная</option>
					<option value="inset">Внутрь</option>
					<option value="outset">Наружу</option>
				</select>
			</label>
			<label><input type="color" v-model="text.color">Цвет текста</label>
			<label><input type="text" v-model="text.size">Размер шрифта текста</label>
			<label><input type="text" v-model="text.padding">Отступы от текста внутренние (сверху, справа, снизу, слева)</label>
			<label><input type="text" v-model="text.margin">Отступы от текста внешние (сверху, справа, снизу, слева)</label>
			<label><input type="text" v-model="picture.padding">Отступы от картинки (сверху, справа, снизу, слева)</label>
		</div>
		<div class="box graphical_4">
			<div class="container">				
				<div class="row">
					<div class="arrow prev"></div>	
					<Column
						v-for="column of getColumns" :key="column.id"
						v-bind:column="column"
						v-bind:valueColumns="+valueColumns"
						v-bind:border="border"
						v-bind:text="text"
						v-bind:picture="picture"
					/>
					<div class="arrow next"></div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import Column from '@/components/Column'

export default {
  data() {
	return {
		border: {
			width: 'px',
			type: 'solid',
			color: '#000000'
		},
		text: {
			color: "",
			size: "px",
			padding: "px px px px",
			margin: "px px px px"
		},
		picture: {
			padding: "px px px px"
		},
		valueColumns: 3,
		valueRows: 1,
		blocksType: 'graphical_4'
	}
  },
  name: 'App',
  components: {
	Column
  },
  computed: {
	getColumns() {
		let result = [];
		
		for (let i = 0 ; i < this.valueColumns * this.valueRows; i++) {
			result.push({id: i+1, title: `Большой живот не от еды! Он уйдёт за 5-10 дней, натощак пейте обычный крепкий...`})
		}

		return result;
	}
  },
  methods: {
	addClass() {
		let select = document.querySelector('.select'),
			box = document.querySelector('.box');

		select.className = `select ${this.blocksType}`;
		box.className = `box ${this.blocksType}`;
	}
  }
  
}
</script>

<style lang="scss">
:focus,
:active {
outline: none;
}

a:focus,
a:active {
outline: none;
}

aside,
nav,
footer,
header,
section {
display: block;
}

html,
body {
height: 100%;
min-width: 320px;
scroll-behavior: smooth;
}

body {
line-height: 1.2;
font-family: Arial;
-ms-text-size-adjust: 100%;
-moz-text-size-adjust: 100%;
-webkit-text-size-adjust: 100%;
}

input,
button,
textarea {
font-family: Arial;
}

input::-ms-clear {
display: none;
}

button {
cursor: pointer;
}

button::-moz-focus-inner {
padding: 0;
border: 0;
}

a {
color: inherit;
font-size: inherit;
}

a,
a:visited {
text-decoration: none;
}

a:hover {
text-decoration: none;
}

ul li {
list-style: none;
}

img {
vertical-align: top;
}

h1,
h2,
h3,
h4,
h5,
h6 {
font-weight: inherit;
font-size: inherit;
margin: 0;
padding: 0;
}

#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	
	.container {
		max-width: 1536.05px;
		margin: 0 auto;
		padding: 0 10px;
		width: 100%;
		text-align: center;
	}
	.row {
		display: flex;
		margin: 0 -10px;
		flex-wrap: wrap;
		justify-content: center;
	}
	input {
		border: 1px solid #000;
		margin: 0px 5px 0px 0px;
		padding: 2px;
	}
	label {
		display: flex;
		text-align: left;
		margin: 0px 0px 10px 0px;
	}
	select {
		border: 1px solid #000;
		display: block;
		margin: 0px 0px 10px 0px;
	}
}
</style>