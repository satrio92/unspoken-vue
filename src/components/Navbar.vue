<template>
	<div id="navbar" class="w-full xl:w-[1100px] py-6 flex justify-between items-center">
		<!-- <div class="w-[120px] h-[40px] bg-white"></div> -->
		<div class="flex gap-3 items-center text-lg tracking-[.2em] text-white font-semibold ">
			<img src="../../public/assets/img/logo.svg" alt="" class="h-[45px]">
			<span>Pixelize</span>
		</div>
		<ul class="flex gap-4 items-center text-lg text-white font-medium">
			<router-link to="/" class="px-10 py-2 rounded-r-md rounded-bl-md" active-class="font-semibold text-[#050915] bg-dropsunrise" exact>Home</router-link> 
			<router-link to="/about" class="px-10 py-2 rounded-r-md rounded-bl-md" active-class="font-semibold text-[#050915] bg-dropsunrise" exact>About</router-link> 
			<router-link to="/contact" class="px-10 py-2 rounded-r-md rounded-bl-md" active-class="font-semibold text-[#050915] bg-dropsunrise" exact>Contact</router-link> 
		</ul>
	</div>
</template>

<script>
export default {
	name: 'Navbar',
	components: {}
}
</script>