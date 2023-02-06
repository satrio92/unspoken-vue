<template>
  <div id="post-card" class="w-full xl:w-[370px] flex flex-col gap-6">
		<img :src="'/assets/posts/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '/img/header.jpg'" :alt="item.title" class="w-full h-[190px] xl:h-[220px] rounded-[12px] xl:rounded-[20px] object-cover">
		<div class="w-full rounded-[12px] xl:rounded-[20px] border-2 hover:border-none border-white hover:bg-black-gradient text-white flex flex-col items-center py-6 px-9 gap-4">
			<p class="text-[11px] xl:text-[12px] font-medium">{{ item.postDate }}</p>
			<p class="text-[15px] xl:text-[16px] text-center font-semibold">{{ item.title }}</p>
			<div class="flex gap-2 items-center">
				<img :src="'/assets/img/author/' + item.author.name.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '.png'" :alt="item.author.name" class="w-5 xl:w-6 h-5 xl:h-6 rounded-full bg-white">
				<p class="text-[11px] xl:text-[12px] font-medium">{{ item.author.name }}</p>
			</div>
			<router-link :to="'/post/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase()" class="w-[160px] xl:w-full h-10 xl:h-16 rounded-[7px] xl:rounded-[10px] bg-dropsunrise flex justify-center items-center text-[14px] xl:text-[18px] text-black font-semibold mt-[9px]">Read More</router-link>
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