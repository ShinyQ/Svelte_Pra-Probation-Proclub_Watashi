<script>
	import Tailwindcss from '../src/Tailwindcss.svelte';
	import { onMount } from "svelte";
	let src =  "./images/"
    const apiURL = "https://jsonplaceholder.typicode.com/todos";
	let data = [];
	onMount(async function() {
		fade()
		typeWriter()
        // const response = await fetch(apiURL);
        // data = await response.json();
	});

	var opacity = 0;
	var intervalID = 0;

	function fade(){
		intervalID = setInterval(hide,20)
	}

	function hide(){
		var img = document.getElementById('watashi');
		opacity = Number(window.getComputedStyle(img).getPropertyValue("opacity"));
		if(opacity>0){
			opacity = opacity + 0.1;
			img.style.opacity = opacity;
		} else {
			clearInterval(intervalID);
		}
	}

	var i = 0;
	var txt = 'Hello Stranger, Welcome To My Blog.';
	var speed = 70;

	function typeWriter() {
	  if (i < txt.length) {
	    document.getElementById("h2-head").innerHTML += txt.charAt(i);
	    i++;
	    setTimeout(typeWriter, speed);
	  }
	}
</script>

<style>
      #menu-toggle:checked + #menu {
        display: block;
      }

			#h2-head{
				font-size: 50px;
				font-weight: 600;
				font-family: Arial, Helvetica, sans-serif
			}

			@media only screen and (max-width: 414px) {
				#h2-head{
					text-align: center;
					font-size: 23px;
					font-weight: 600;
					font-family: Arial, Helvetica, sans-serif;
					margin: 10px;
				}
			}
</style>

<body class="antialiased bg-gray leading-normal tracking-normal">
  <div id="div-watashi" class="flex justify-center mt-20">
  	<img id="watashi" width="200" src="{src}watashi.png" alt="">
  </div>
	<div class="flex justify-center">
		<h2 class="pt-5 pb-5" id="h2-head"></h2>
	</div>

	<div class="flex justify-center">
  	<img class="mt-20" width="200" src="{src}proclub.png" alt="">
  </div>
</body>
