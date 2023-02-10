<template>
  <div id="app">
    <div class="container">
      <h1>{{ TitleAll }}</h1>
      <p class="text-error" v-show="isErrorShow">{{ ErrorText }}</p>
        <inputButton
          @createName="createName"
          @errorInput="errorInput"
        />
        <inputSearchName
          :updateAllNameHandler="updateAllNameHandler"
        />
        <addNameComponents
          :allName="searchNameFilter(allName, allNameFilter)"
          @onRemove="onRemoveHandler"
        />
        <mixinsOne />
        <mixinsTwo />
    </div>
  </div>
</template>

<script>

import addNameComponents from './components/addNameComponents.vue'
import inputButton from './components/inputButton.vue'
import searchName from './components/searchName.vue'
import mixinsOne from './components/mixinsOne.vue'
import mixinsTwo from './components/mixinsTwo.vue'

export default {
  name: 'App',
  components: {
    addNameComponents,
    inputButton,
    inputSearchName: searchName,
    mixinsOne,
    mixinsTwo,
  },
  data() {
		return {
      isErrorShow: false,
      TitleAdd: 'Add',
      TitleName: 'Name',
      TitleList: 'List',
      ErrorText: 'Add name please !!!',
			allName: [
				{
					name: 'Jaloliddin',
					id: 1,
				},
				{
					name: 'Baxtiyor',
					id: 2,
				},
				{
					name: 'Nail',
					id: 3,
				},
        {
					name: 'Akmal',
					id: 4,
				},
				{
					name: 'Humoyun',
					id: 5,
				},
				{
					name: 'Nodir',
					id: 6,
				},
        {
					name: 'Jeka',
					id: 7,
				},
        {
					name: 'Abdulhay',
					id: 8,
				},
        {
					name: 'Timur',
					id: 9,
				},
        {
					name: 'Shuxrat',
					id: 10,
				},
			],
      allNameFilter: '',
		}
  },
  methods: {
    createName(item) {
      this.allName.push(item)
    },
    onRemoveHandler(id) {
      this.allName = this.allName.filter(item => item.id !== id)
    },
    errorInput(isShow) {
      this.isErrorShow = isShow
    },
    searchNameFilter(arr, allNameFilter) {
      if(allNameFilter.length == 0) {
        return arr
      }
      return arr.filter(c => c.name.toLowerCase().indexOf(allNameFilter) > -1)
    },
    updateAllNameHandler(allNameFilter) {
      this.allNameFilter = allNameFilter
    }
  },
  computed: {
    TitleAll() {
      return this.TitleAdd + ' ' + this.TitleName + ' ' + this.TitleList
    },
  }
}

</script>

<style>

body{
  background: #f8f9fa;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px 0;
}
.container .text-error{
  position: absolute;
  font-size: 15px;
  top: 170px;
  color: red;
  /* display: none; */
}
.content-box{
  width: 100%;
  display: flex;
  background: #f2f2f2;
}
</style>
