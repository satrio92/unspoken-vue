<template>
	<div id="home" class="w-full h-[400px] px-24 bg-black-gradient">
		<header>
			<Navbar />
			<FeaturedPost />
		</header>
	</div>
</template>

<script>

import FeaturedPost from '../components/FeaturedPost.vue';
import Navbar from '../components/Navbar.vue'

export default {
	name: 'Home',
	components: {
    Navbar,
    FeaturedPost
}
}
</script>