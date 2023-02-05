<template>
  <div id="post-card" class="flex flex-col gap-6">
		<img :src="'/assets/posts/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '/img/header.jpg'" :alt="item.title" class="w-[370px] h-[220px] rounded-[20px] object-cover">
		<div class="w-[370px] rounded-[20px] border-2 hover:border-none border-white hover:bg-black-gradient text-white flex flex-col items-center py-6 px-9 gap-4">
			<p class="text-xs font-medium">{{ item.postDate }}</p>
			<p class="text-center font-semibold">{{ item.title }}</p>
			<div class="flex gap-2 items-center">
				<img src="" alt="" class="w-6 h-6 rounded-full bg-white">
				<p class="text-xs font-medium">{{ item.author.name }}</p>
			</div>
			<router-link :to="'/post/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase()" class="w-full h-16 rounded-[10px] bg-blue-gradient flex justify-center items-center text-lg text-black font-medium mt-[9px]">Read More</router-link>
		</div>
	</div>
</template>

<script>
export default {
	name: 'PostCard',
	components: {},
	props: ['item']
}
</script>