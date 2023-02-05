<template>
  <div id="author" class="w-full xl:w-[776px] flex flex-col items-center bg-black-gradient rounded-[20px] text-white text-center gap-3 pt-[60px] pb-10 px-20 relative">
		<span class="text-2xl font-bold">{{ author.name }}</span>
		<span class="text-sm italic">{{ '"' + author.bio + '"' }}</span>
		<img :src="'/assets/img/author/' + author.name.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '.png'" :alt="author.name" class="w-[76px] h-[76px] rounded-full border-2 border-white absolute -top-[38px]">
	</div>
</template>

<script>
export default {
	name: 'Author',
	components: {},
	props: ['author']
}
</script>