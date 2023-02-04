<template>
	<div id="home" class="w-full px-12 pb-12 bg-[#050915] font-poppins">
		<header>
			<Navbar />
			<FeaturedPost :postData="postData"/>
		</header>
		<div class="w-full flex flex-col xl:flex-row gap-[52px] relative justify-center pt-44">
			<!-- POSTS -->
			<div class="w-full justify-center xl:justify-start xl:w-[776px] flex gap-9 flex-wrap">
				<PostCard :item="item" v-for="item in postData" :key="item.id"/>
			</div>
			<!-- Posts Widget -->
			<div class="w-full items-center xl:items-start xl:w-[370px] h-[605px] xl:sticky top-6 flex flex-col gap-[25px]">
				<PostWidget :postData="postData"/>
				<Category />
			</div>
		</div>
		<!-- <div id="footer" class="w-full h-28 bg-green-500"></div> -->
	</div>
</template>

<script>
import Category from '../components/Category.vue';
import FeaturedPost from '../components/FeaturedPost.vue';
import Navbar from '../components/Navbar.vue'
import PostCard from '../components/PostCard.vue';
import PostWidget from '../components/PostWidget.vue';
import postData from '../posts'

export default {
	name: 'Home',
	components: {
		Navbar,
		FeaturedPost,
		PostWidget,
		Category,
		PostCard
	},
	data() {
		return {
			postData: postData,
		}
	},
	methods: {
	},
	mouted() {
	}
}
</script>