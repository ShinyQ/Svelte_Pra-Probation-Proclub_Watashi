<script>
	import Tailwindcss from './Tailwindcss.svelte';
	import { onMount } from "svelte";
	const apiURL = "https://newsapi.org/v2/top-headlines?apiKey=f8fd87d48cf746e0a817a4f7a21bafe4&category=technology&pageSize=6";
	let data = [];

	onMount(async function() {
		const response = await fetch(apiURL);
    data = await response.json();
	});

	console.log(data);
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

<body class="antialiased mx-10 mt-5">
		<h1 id="h1-head" class="mt-8"> Some Post That I Found Interesting... </h1>

		<div class="flex mb-4">

		{#each data as item }
			<div class="w-1/3">
				<div class="px-4">
					<div class="bg-white rounded-lg mx-auto my-4 p-12">
							<h1 class="text-2xl font-medium mb-2">Hello</h1>
							Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum illo cupiditate molestias atque consequuntur ea quo cumque, odit velit sint similique? Asperiores ratione aperiam tempora, alias corrupti deleniti quaerat molestiae.
					</div>
				</div>
			</div>
		{/each}
			<!-- <div class="w-1/3">
				<div class="px-4">
					<div class="bg-white rounded-lg mx-auto my-4 p-12">
							<h1 class="text-2xl font-medium mb-2">Hello</h1>
							Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum illo cupiditate molestias atque consequuntur ea quo cumque, odit velit sint similique? Asperiores ratione aperiam tempora, alias corrupti deleniti quaerat molestiae.
					</div>
				</div>
			</div>
			<div class="w-1/3">
				<div class="px-4">
					<div class="bg-white rounded-lg mx-auto my-4 p-12">
							<h1 class="text-2xl font-medium mb-2">Hello</h1>
							Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum illo cupiditate molestias atque consequuntur ea quo cumque, odit velit sint similique? Asperiores ratione aperiam tempora, alias corrupti deleniti quaerat molestiae.
					</div>
				</div>
			</div>
			<div class="w-1/3">
				<div class="px-4">
					<div class="bg-white rounded-lg mx-auto my-4 p-12">
							<h1 class="text-2xl font-medium mb-2">Hello</h1>
							Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum illo cupiditate molestias atque consequuntur ea quo cumque, odit velit sint similique? Asperiores ratione aperiam tempora, alias corrupti deleniti quaerat molestiae.
					</div>
				</div>
			</div> -->
		</div>
</body>
