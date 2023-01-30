<template>
	<div id="home" class="w-full h-[1000px] px-36 bg-black-gradient font-poppins">
		<header>
			<Navbar />
			<FeaturedPost :postData="postData"/>
		</header>
	</div>
</template>

<script>

import FeaturedPost from '../components/FeaturedPost.vue';
import Navbar from '../components/Navbar.vue'
import postData from '../posts'

export default {
	name: 'Home',
	components: {
    Navbar,
    FeaturedPost
	},
	data() {
		return {
			postData: postData
		}
	},
	methods: {
	}
}
</script>