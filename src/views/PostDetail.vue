<template>
	<div id="post-detail"  class="w-full px-12 pb-12 bg-[#050915] font-poppins">
		<header>
			<Navbar />
		</header>
		<div class="w-full flex gap-[52px] relative justify-center pt-12">
			<div class="w-[776px] bg-black-gradient flex flex-col gap-16 rounded-[20px] py-8 px-8 text-white ">
				<div class="w-full flex flex-col gap-4 items-center">
					<img :src="'/assets/img/posts/' + thePost[0].title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '/header.jpg'" :alt="thePost[0].title" class="w-full h-[350px] bg-white rounded-2xl object-cover">
					<div class="flex items-center text-sm gap-4">
						<p>{{ thePost[0].postDate }}</p>
						<div class="flex items-center gap-2">
							<img src="#" alt="" class="w-6 h-6 rounded-full bg-white">
							<p>{{ thePost[0].author.name }}</p>
						</div>
					</div>
					<h1 class="text-2xl text-center font-bold">{{ thePost[0].title }}</h1>
				</div>
				<div class="text-white flex flex-col gap-5 px-6">
					<p>Are you tired of spending hours searching for design inspiration? Midjourney is here to help. This innovative tool uses a combination of machine learning algorithms and human creativity to generate unique images that can be used as a starting point for your design projects. Whether you're a professional designer or just starting out, Midjourney can help you find inspiration and generate images that meet your design requirements.</p>
					<p>How to Use Midjourney to Generate Images for Design Inspiration</p>
					<ol class="flex flex-col gap-3 list-decimal ml-3">
						<li class="pl-2">Sign up for an account: You will need to sign up for a Midjourney account to start using the platform. The sign-up process is quick and simple, taking just a few minutes.</li>
						<li class="pl-2">Choose a design category: Midjourney offers a wide range of design categories to choose from, including logos, graphics, illustrations, and more. Choose the category that best matches your design needs.</li>
						<li class="pl-2">Enter your design requirements: Once you have chosen your design category, you will need to enter your design requirements. This includes the desired color palette, design style, and any other specific requirements you may have.</li>
						<li class="pl-2">Let Midjourney generate images: Midjourney uses its algorithms and human designers to generate a set of images that meet your requirements. You can preview these images and choose the one that best fits your design needs.</li>
						<li class="pl-2">Download your image: Once you have chosen your image, you can download it in a variety of formats, including PNG, JPG, and SVG. You can then use the image as a starting point for your design project.</li>
					</ol>
					<p>Why Choose Midjourney for Design Inspiration</p>
					<p>Midjourney is an innovative tool that helps designers save time and effort in their design process. With its user-friendly interface, wide range of design categories, and customizable options, Midjourney provides designers with a valuable resource for finding design inspiration and generating images for their projects. Whether you're a seasoned designer or just starting out, Midjourney is a tool that can help you achieve your design goals with ease.</p>
					<p>So why wait? Sign up for Midjourney today and start generating images for your design projects!</p>
				</div>
			</div>
			<div class="w-[370px] h-[605px] sticky top-6 flex flex-col gap-[25px]">
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
			postData: postData
		}
	},
	methods: {},
	computed: {
		thePost() {
			return this.postData.filter(object => object.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() === this.$route.params.post);
		}
	}
}
</script>