<template>
	<div id="home" class="w-full h-[2000px] px-12 bg-black-gradient font-poppins">
		<header>
			<Navbar />
			<FeaturedPost :postData="postData"/>
		</header>
		<div class="w-full flex gap-[52px] relative justify-center">
			<!-- POSTS -->
			<div class="w-[776px] h-[1000px] bg-pink-300"></div>
			<!-- Posts Widget -->
			<div class="w-[370px] h-[605px] sticky top-6 flex flex-col gap-[25px]">
				<PostWidget :postData="postData"/>
				<Category />
			</div>

		</div>
	</div>
</template>

<script>
import Category from '../components/Category.vue';
import FeaturedPost from '../components/FeaturedPost.vue';
import Navbar from '../components/Navbar.vue'
import PostWidget from '../components/PostWidget.vue';
import postData from '../posts'

export default {
	name: 'Home',
	components: {
		Navbar,
		FeaturedPost,
		PostWidget,
		Category
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