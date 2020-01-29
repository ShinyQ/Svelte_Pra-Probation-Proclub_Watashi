<!-- App.svelte -->
<script>
  import { Router, Link, Route } from "svelte-routing";
  import Home from "./Home.svelte";
  import Blog from "./Blog.svelte";
  import About from "./About.svelte";
  import Favorite from "./Favorite.svelte";
  import Tailwindcss from './Tailwindcss.svelte';
  export let url = "";
</script>

<style>
  #menu-toggle:checked + #menu {
    display: block;
  }
</style>

<Router url="{url}">
	<header class="sticky top-0 shadow-lg lg:px-20 px-6 bg-white flex flex-wrap items-center lg:py-0 py-2">
		<div class="flex-1 flex justify-between items-center">
			<a href="#">
				<svg width="225.129" height="36.101" viewBox="0 0 449 72">
				<defs>
					<style>.cls-1 {
						font-size: 100px;
						fill: #ff4040;
						text-anchor: middle;
						font-family: Magneto;
						font-weight: 700;
					}
					</style>
				</defs>
				<text id="Watashi" class="cls-1" x="223" y="68.528">
					<tspan x="223">Watashi</tspan>
				</text>
				</svg>
			</a>
		</div>
			<label for="menu-toggle" class="pointer-cursor lg:hidden block">
        <svg class="fill-current text-gray-900" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20">
          <title>menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"></path>
        </svg>
      </label>
      <input class="hidden" type="checkbox" id="menu-toggle">
				<div class="hidden lg:flex lg:items-center lg:w-auto w-full svelte-1c262bi" id="menu">
    			<nav>
    				<ul class="lg:flex items-center justify-between text-base text-gray-700 pt-4 lg:pt-0">
    					<a class="lg:p-4 py-3 px-0 block border-b-2 border-transparent hover:text-red-600 hover:border-red-600 lg:mb-0 mb-2" href="/"><li><Link to="/" >Home</Link></li></a>
    					<a class="lg:p-4 py-3 px-0 block border-b-2 border-transparent hover:text-red-600 hover:border-red-600 lg:mb-0 mb-2" href="/blog"><li><Link to="/blog" >Blog</Link></li></a>
    					<a class="lg:p-4 py-3 px-0 block border-b-2 border-transparent hover:text-red-600 hover:border-red-600 lg:mb-0 mb-2" href="/"><li><Link to="/" >Favorite</Link></li></a>
    					<a class="lg:p-4 py-3 px-0 block border-b-2 border-transparent hover:text-red-600 hover:border-red-600 lg:mb-0 mb-2" href="/"><li><Link to="/" >About Me</Link></li></a>
    				</ul>
    			</nav>
		    </div>
	</header>

  <div>
    <Route path="/"><Home /></Route>
	  <Route path="/blog"><Blog /></Route>
    <Route path="/favorite"><Favorite /></Route>
    <Route path="/about"><About /></Route>
  </div>
</Router>
