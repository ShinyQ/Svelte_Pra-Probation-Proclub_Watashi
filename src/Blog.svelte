<script>
	import Tailwindcss from './Tailwindcss.svelte';
	import { onMount } from "svelte";
	import axios from 'axios'
	const apiURL = "https://newsapi.org/v2/top-headlines?country=us&apiKey=f8fd87d48cf746e0a817a4f7a21bafe4&category=technology&pageSize=6";
	let data = [];

	onMount((async ()=>{
		const response = await axios(apiURL)
		data = response.data.articles
		console.log(data)
	})());

</script>

<style>
      #menu-toggle:checked + #menu {
        display: block;
      }


			#h1-head{
				font-size: 30px;
				font-weight: 600;
				font-family: Arial, Helvetica, sans-serif
			}
  </style>

<body class="antialiased lg:mx-40 mt-5">
		<div class="px-6">
			<h1 id="h1-head" class="mt-8"> Some Post That I Found Interesting... </h1>
			<div class="flex flex-wrap -mx-2 mb-8">
				{#each data as item }
	      <div class="w-full md:w-1/2 lg:w-1/3 lg:px-2">
					<div style="min-height:450px;" class="bg-white rounded-lg mx-auto my-4 p-6">
							<img style="min-height:200px; max-height:200px" class="mb-5" width="100%" src="{item.urlToImage}" alt="">
							<h1 class="text-2xl font-medium mb-2">{item.title.substring(0,40)}....</h1>
								{item.description.substring(0,105)}...
					</div>
	      </div>
				{/each}
	   </div>
	 </div>

</body>
