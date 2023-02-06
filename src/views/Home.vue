<template>
	<div id="home" class="w-full px-4 xl:px-12 pb-12 bg-[#050915] font-poppins flex flex-col items-center gap-24">
		<header class="w-full xl:w-auto">
			<Navbar />
			<FeaturedPost :postData="postData"/>
		</header>
		<div class="w-full flex flex-col xl:flex-row gap-[52px] relative justify-center">
			<!-- POSTS -->
			<div class="w-full justify-center xl:justify-start xl:w-[776px] flex gap-9 flex-wrap">
				<PostCard :item="item" v-for="item in postData" :key="item.id"/>
			</div>
			<!-- Posts Widget -->
			<div class="w-full items-center xl:items-start xl:w-[370px] h-[605px] xl:sticky top-6 flex flex-col gap-[25px]">
				<PostWidget :postData="postData" :data="'recent'"/>
				<Category />
			</div>
		</div>
		<Footer />
	</div>
</template>

<script>
import Category from '../components/Category.vue';
import FeaturedPost from '../components/FeaturedPost.vue';
import Footer from '../components/Footer.vue';
import Navbar from '../components/Navbar.vue';
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
    PostCard,
    Footer
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