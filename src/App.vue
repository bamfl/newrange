<template>
  <div id="app">
	  <div class="container">
	  	<div>
			<label><input type="range" min="1" max="5" step="1" v-model="valueColumns">Кол-во колонок: {{ valueColumns }}</label>
			<label><input type="range" min="1" max="3" step="1" v-model="valueRows">Кол-во рядов: {{ valueRows }}</label>
			<label><input type="text" v-model="border.width">Толщина рамки</label>
			<label><input type="color" v-model="border.color">Цвет рамки</label>
			<select v-model="border.type">
				<option value="solid" selected>Сплошная</option>
				<option value="dotted">Пунктирная</option>
				<option value="dashed">Штриховая</option>
				<option value="double">Двойная</option>
				<option value="groove">Вдавленная</option>
				<option value="ridge">Рельефная</option>
				<option value="inset">Внутрь</option>
				<option value="outset">Наружу</option>
			</select>
			<label><input type="color" v-model="text.color">Цвет текста</label>
			<label><input type="text" v-model="text.size">Размер шрифта текста</label>
			<label><input type="text" v-model="text.padding">Отступы от текста (сверху, справа, снизу, слева)</label>
			<label><input type="text" v-model="picture.padding">Отступы от картинки (сверху, справа, снизу, слева)</label>
		</div>

		<div class="row">
			<Column
				v-for="column of getColumns" :key="column.id"
				v-bind:column="column"
				v-bind:valueColumns="+valueColumns"
				v-bind:border="border"
				v-bind:text="text"
				v-bind:picture="picture"
			/>
		</div>
	  </div>
  </div>
</template>

<script>
import Column from '@/components/Column'

export default {
  data() {
	return {
		columns: [
			{id: 1, title: 'Колонка 1'},
			{id: 2, title: 'Колонка 2'},
			{id: 3, title: 'Колонка 3'},
			{id: 4, title: 'Колонка 4'},
			{id: 5, title: 'Колонка 5'}
		],
		border: {
			width: '0px',
			type: 'solid',
			color: '#000'
		},
		text: {
			color: '#000',
			size: "20px",
			padding: "0px 0px 0px 0px"
		},
		picture: {
			padding: "0px 0px 0px 0px"
		},
		valueColumns: 3,
		valueRows: 1
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
			result.push({id: i+1, title: `Колонка ${i}`})
		}

		return result;
	}
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
	padding: 0px;
	margin: 0px;
	border: 0px;
}
*,
*:before,
*:after {
	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}
.container {
	max-width: 1230px;
	padding: 0 15px;
	margin: 0 auto;
}
.row {
	display: flex;
	margin: 0 -10px;
	flex-wrap: wrap;
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
</style>