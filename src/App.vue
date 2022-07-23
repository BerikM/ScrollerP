<template> 
	
	<div class="main">
		<button class="btn" @click="upp" > Выше</button>
			<div class="inner" v-for="object in objects.slice(0,maxslice)">
			<h3>{{object.text}}</h3> <img src="../smallimg.png" alt="">
			</div>
		<button class="btn" @click="down"> Ниже</button>
	</div>
	
	

</template>


<script>
export default{
	data(){
		return{
			maxslice: 7,
			objects:[
				{id: 1, text: 'Элемент 1'},
				{id: 2, text: 'Элемент 2'},
				{id: 3, text: 'Элемент 3'},
				{id: 5, text: 'Элемент 4'},
				{id: 6, text: 'Элемент 5'},
				{id: 7, text: 'Элемент 6'},
				{id: 8, text: 'Элемент 7'},
				{id: 9, text: 'Элемент 8',},
				{id: 10, text: 'Элемент 9'},
				{id: 11, text: 'Элемент 10'},
				{id: 12, text: 'Элемент 11'},
				{id: 13, text: 'Элемент 12'},
				{id: 14, text: 'Элемент 13'},
				{id: 15, text: 'Элемент 14'},
			],
		}
	},
	methods:{

		upp(){
			
			const a = this.objects[this.objects.length-1]
			this.objects.pop()
			this.objects.unshift(a)
		
		},
		down(){
			const b = this.objects[0]
			this.objects.shift(1)
			this.objects.push(b)
		}
	} 
}
</script>


<style>
* {
	padding: 0px;
	margin: 0px;
}
.main{
	max-width: 40%;
	display: grid;
	grid-template-columns: 1;
	grid-gap: 2px;
	margin: 0 auto;
	text-align: center;
}
.inner{
	padding-top: 15px;
	background-color: rgb(148, 120, 120);
}

.inner:nth-child(5){
	background-color: rgb(141, 19, 19);
	border-radius: 5px;

}

.inner:nth-child(2), .inner:nth-child(3), .inner:nth-child(4), .inner:nth-child(6), .inner:nth-child(7),.inner:nth-child(8){
	min-width: 99%;
	margin: 0 auto;
}

.btn{
	margin: 20px auto;
	padding: 10px 30px;
	background-color: rgb(175, 235, 215);
}

</style>