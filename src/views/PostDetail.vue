<template>
	<div id="post-detail"  class="w-full px-6 xl:px-12 pb-12 bg-[#050915] font-poppins">
		<header>
			<Navbar />
		</header>
		<div class="w-full flex flex-col xl:flex-row gap-[52px] relative justify-center pt-12">
			<div class="w-full xl:w-[776px] bg-black-gradient flex flex-col gap-16 rounded-[20px] py-8 px-3 xl:px-8 text-white ">
				<div class="w-full flex flex-col gap-4 items-center">
					<img :src="'/assets/img/posts/' + thePost[0].title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '/header.jpg'" :alt="thePost[0].title" class="w-full h-[200px] xl:h-[350px] bg-white rounded-2xl object-cover">
					<div class="flex items-center text-sm gap-4">
						<p class="text-sm xl:text-base">{{ thePost[0].postDate }}</p>
						<div class="flex items-center gap-2">
							<img src="#" alt="" class="w-6 h-6 rounded-full bg-white">
							<p class="text-sm xl:text-base">{{ thePost[0].author.name }}</p>
						</div>
					</div>
					<h1 class="text-[22px] xl:text-2xl text-center font-bold">{{ thePost[0].title }}</h1>
				</div>
				<div class="text-white flex flex-col gap-5 px-6 text-sm xl:text-base" v-html="article"></div>
			</div>
			<div class="w-full items-center xl:items-start xl:w-[370px] h-[605px] sticky top-6 flex flex-col gap-[25px]">
				<PostWidget :postData="postData"/>
				<Category />
			</div>
		</div>
	</div>
</template>

<script>
import Category from '../components/Category.vue';
import Navbar from '../components/Navbar.vue'
import PostWidget from '../components/PostWidget.vue';
import postData from '../posts'

export default {
	name: 'PostDetail',
	components: {
		Navbar,
		Category,
		PostWidget
	},
	data() {
		return {
			postData: postData,
			article: ""
		}
	},
	methods: {},
	computed: {
		thePost() {
			return this.postData.filter(object => object.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() === this.$route.params.post);
		}
	},
	  mounted() {
		// fetch the article HTML file from your local storage
		fetch('/assets/img/posts/'+ this.$route.params.post +'/article.html')
		.then(response => response.text())
		.then(article => {
			this.article = article, console.log(article)
		});
	}
}
</script>