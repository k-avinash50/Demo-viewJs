
<template>
	<div class="Container" id="nosty">
		<div id="header" >
			<h1>Welcome to the Gaming World</h1>
		</div>
		<div class="row">
			<div class="column">
				<div class="box bg-light">
					<img id="man" src="./assets/15779.jpg" alt="game1" />
					<div class="row">
						<div class="col-6">Name :</div>
						<div class="col-6">Bat Man</div>
						<div class="col-6">Storage :</div>
						<div class="col-6">12 GB</div>
						<div class="col-6">Likes :</div>
						<div class="col-6">
							{{ Count }}
							<span v-if="like === true">
								<i class="fas fa-heart" id="heart"></i
							></span>
						</div>
					</div>
				</div>
				<div class="row">
					<div class="col-lg-1">
						<button v-bind:style="{ background: like == false  ? '#1877f2':'#FF4500'}"  v-on:click="Count1(1)">
							<span>{{ like == false  ? "Like" : "DisLike" }}</span> <i   :class=logo />
						</button>
						
					</div>
					
				</div>
			
		</div>
		<div class="column">
			<feedback :like="like"></feedback>
		</div>	
		</div>
	</div>
</template>

<script>
    import feedback from "@/components/feedback"

	export default {
		components:{
			"feedback":feedback

			},
		name: "app",
		
		data() {
			return {
				Count: 400,
				
				like: "",
				message:"",
				logo:"",
				
				
			};
		},
		methods: {
			
			Count1(ino) {
				if (this.like == false || this.like=="a") {
					this.Count += ino;
					this.like = true;
					this.logo='fas fa-thumbs-down'
				} else {
					this.Count += -ino;
					this.like = false;
					this.logo='fas fa-thumbs-up'
				}
			},
		},
	};
</script>

<style>
	#header {
		background: black;
		height: 60px;
		color: white;
		text-align: center;
		font-weight: bold;
	}
	.box {
		width: 260px;
		height: 260px;
		margin: 4px;
		border-radius: 6px;
		border: 2px solid royalblue;
		box-shadow: 10px 10px 5px grey;
	}
	button{
		margin-left: 6px;
		margin-top: 10px;
		font-weight: bold;
		font-size: 20px;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		cursor: pointer;
		background: #1877f2;
		box-shadow: 10px 10px 5px grey;

	}
	button:hover{
		background-color: lightcoral;
	}
	.col-6{
		float: left;
		width: 42%;
		margin: 8px;
	}
	.column{
		float: left;
		width: 42%;
		margin: 8px;
	}
	#man {
		width: 100%;
		height: 140px;
		
	}
	#heart {
		color: red;
	}
	@media screen and (max-width: 600px) {
   #header {
	width:100%;
    height: 80px;
  }
  .box {
		width: 92%;
  }
  .column{
		float: left;
		width: 100%;
		
	}
}
</style>
