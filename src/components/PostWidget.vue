<template>
    <div id="post-widget" class="flex flex-col items-center gap-5 bg-black-gradient rounded-[20px] py-7 w-full text-white">
        <h4 class="text-[28px] font-bold">Recent Post</h4>
        <div class="flex flex-col">
            <div class="flex items-center gap-3 py-4 border-t border-t-white" v-for="item in 3" :key="item.id">
                <img src="#" alt="#" class="w-[40px] h-[40px] rounded-full bg-pink-300">
                <div class="flex flex-col w-[220px] gap-1">
                    <p class="text-xs font-medium">Money makes your life easier. If you're lucky to have it, you're lucky.</p>
                    <p class="text-[10px]">{{ postData[0].postDate }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PostWidget",
    components: {},
    props: ['postData']
}
</script>