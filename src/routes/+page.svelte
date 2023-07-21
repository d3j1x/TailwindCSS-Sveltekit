<script>
	import lsm from '$lib/img/logosm.jpg';
	
	// const burger = document.querySelector('#burger');
	// const menu = document.querySelector('#menu');

	// burger.addEventListener('click', () => {
	// 	if(menu.classList.contains('hidden')) {
	// 		menu.classList.remove('hidden');
	// 	} else {
	// 		menu.classList.add('hidden');
	// 	}
	// })

	

	let isOpen = false;

	const toggleMenu = () => {
  		isOpen = !isOpen;
	};


	import { onMount } from 'svelte';

let isMobile = false;

onMount(() => {
  const mediaQuery = window.matchMedia('(max-width: 768px)');
  updateMediaQuery(mediaQuery);

  mediaQuery.addListener(updateMediaQuery);

  return () => mediaQuery.removeListener(updateMediaQuery);
});

function updateMediaQuery(mediaQuery) {
  isMobile = mediaQuery.matches;
	if (!isMobile) {
		isOpen = true;
	}
}

	
	



</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>


<div>
<div class="grid md:grid-cols-3 lg:grid-cols-4">
	<div class="md:col-span-1 md:flex md:justify-end">
		<nav class="text-right">
			<div class="flex justify-between items-center">
				<h1 class="font-bold uppercase p-4 border-b border-gray-100">
					<a href="/" class="hover:text-gray-700 text-green-500 sm:text-red-500 md:text-yellow-500 lg:text-blue-500 ">Food Ninja</a>
				</h1>
				<div class="px-4 cursor-pointer md:hidden" id="burger" on:click={toggleMenu}>
					<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
						<path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
					  </svg>					  
				</div>
			</div>

			{#if isOpen}
			<ul class="text-sm mt-6  md:block" id="menu">
				<li class="text-gray-700 font-bold">
					<a href="/" class="px-4 flex justify-end py-1 border-r-4 border-primary">
						<span>Home</span>
						<svg style="margin-left: 1rem;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
							<path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
						  </svg>
					</a>
				</li>
				<li>
					<a href="/" class="px-4 flex justify-end py-1 border-r-4 border-white">
						<span>About</span>
						<svg style="margin-left: 1rem;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
							<path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z" />
						  </svg>						  
					</a>
				</li>
				<li>
					<a href="/" class="px-4 flex justify-end py-1 border-r-4 border-white">
						<span>Contact</span>
						<svg style="margin-left: 1rem;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
							<path stroke-linecap="round" stroke-linejoin="round" d="M21.75 9v.906a2.25 2.25 0 01-1.183 1.981l-6.478 3.488M2.25 9v.906a2.25 2.25 0 001.183 1.981l6.478 3.488m8.839 2.51l-4.66-2.51m0 0l-1.023-.55a2.25 2.25 0 00-2.134 0l-1.022.55m0 0l-4.661 2.51m16.5 1.615a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V8.844a2.25 2.25 0 011.183-1.98l7.5-4.04a2.25 2.25 0 012.134 0l7.5 4.04a2.25 2.25 0 011.183 1.98V19.5z" />
						  </svg>						  
					</a>
				</li>
			</ul>
			{/if}
		</nav>
	</div> <!-- end nav -->

	<main class="px-16 py-6 bg-gray-100 md:col-span-2 lg:col-span-3">
		<div class="flex justify-center md:justify-end">
			<a href="/" class="btn text-primary border-primary md:border-2 hover:bg-black hover:text-primary transition ease-linear duration-500">Log in</a>
			<a href="/" class="btn text-secondary-200 ml-2 border-primary md:border-2 hover:bg-black hover:text-secondary-200 transition ease-out duration-500">sign up</a>
		</div>

		<!-- <div>
			<div class="bg-red-500 h-4 w-6"></div>
			<div class="bg-blue-500 h-8 w-6"></div>
			<div class="bg-green-500 h-12 w-6"></div>
		</div>

		<div class="flex items-end">
			<div class="bg-red-500 h-4 w-6"></div>
			<div class="bg-blue-500 h-8 w-6"></div>
			<div class="bg-green-500 h-12 w-6"></div>
		</div>

		<br> -->

		<div class="flex items-center justify-center">
			<div class="bg-red-500 h-4 w-6"></div>
			<div class="bg-blue-500 h-8 w-6"></div>
			<div class="bg-green-500 h-12 w-6"></div>
		</div>

		<header>
			<h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
			<h3 class="text-2xl font-semibold">For Ninjas</h3>
		</header>

		<div>
			<h4	class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

			<div class="mt-8 grid lg:grid-cols-3 gap-10">
				<!-- cards go here -->
				<!-- <div class="bg-white rounded overflow-hidden shadow-md relative"> -->
				<div class="card hover:shadow-lg">
					<img src={lsm} alt="logoSM" class="w-full h-32 sm:h-60 object-cover">
					<div class="m-4">
					 <span class="font-bold">01 Bean Chilli Stew</span>
					 <span class="block text-gray-500 text-sm">Recipe By Mario</span>
					</div>

					<!-- <div class="bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2"> -->
						<div class="badge">
							<svg style="display:inline-block" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
								<path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z" />
							</svg>
							  
							<span>25 mins</span>
						</div>
				</div>

				<div class="card hover:shadow-xl">
					<img src={lsm} alt="logoSM" class="w-full h-32 sm:h-60 object-fill">
					<div class="m-4">
					 <span class="font-bold">02 Bean Chilli Stew</span>
					 <span class="block text-gray-500 text-sm">Recipe By Mario</span>
					</div>

					<!-- <div class="bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2"> -->
						<div class="badge">
							<svg style="display:inline-block" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
								<path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z" />
							</svg>	
							<span>25 mins</span>
						</div>
				</div>

				<div class="card hover:shadow-2xl">
					<img src={lsm} alt="logoSM" class="w-full h-32 sm:h-60 object-contain">
					<div class="m-4">
					 <span class="font-bold">03 Bean Chilli Stew</span>
					 <span class="block text-gray-500 text-sm">Recipe By Mario</span>
					</div>

					<!-- <div class="bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2"> -->
						<div class="badge">	
							<svg style="display:inline-block" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
								<path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z" />
							</svg>
							<span>25 mins</span>
						</div>
				</div>
			</div>

			<h4 class="font-bold mt-12 pb-2  border-b border-gray-200">Most Popular</h4>

			<div class="mt-8">
				<!-- cards go here -->
			</div>

			<div class="flex justify-center">
				<div class="btn bg-secondary-100 text-secondary-200 hover:shadow-inner  transform hover:scale-125 hover:bg-opacity-50 transition ease-out duration-400">Load more</div>
			</div>
		</div>
	</main>
</div>

<svg style="width: 10rem; height:10rem; color:red;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
	<path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18.75a60.07 60.07 0 0115.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 013 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 00-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 01-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 003 15h-.75M15 10.5a3 3 0 11-6 0 3 3 0 016 0zm3 0h.008v.008H18V10.5zm-12 0h.008v.008H6V10.5z" />
</svg>

<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
	<path stroke-linecap="round" stroke-linejoin="round" d="M15 11.25l-3-3m0 0l-3 3m3-3v7.5M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
  </svg>

  <button on:click={toggleMenu}>
	{isOpen ? 'Close Menu' : 'Open Menu'}
  </button>
  
  {#if isMobile}
  <p>This is a mobile view.</p>
{:else}
  <p>This is a desktop view.</p>
{/if}
</div>


<style>

</style>