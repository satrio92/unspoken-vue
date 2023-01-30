<template>
	<div id="navbar" class="w-full py-6 flex justify-between items-center">
		<div class="w-[120px] h-[40px] bg-white"></div>
		<ul class="flex gap-24 items-center text-white font-medium">
			<router-link to="/">Home</router-link> 
			<router-link to="/">Category</router-link> 
			<router-link to="/">Contact</router-link> 
		</ul>
	</div>
</template>

<script>
export default {
	name: 'Navbar',
	components: {}
}
</script>