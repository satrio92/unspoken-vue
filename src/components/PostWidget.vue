<template>
    <div id="post-widget" class="flex flex-col items-center gap-5 bg-black-gradient rounded-[20px] py-7 w-full text-white">
        <h4 class="text-[28px] font-bold">{{ title }}</h4>
        <div class="flex flex-col">
            <router-link :to="'/post/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase()" class="flex items-center gap-3 py-4 border-t border-t-white" v-for="item in myPosts.slice(-3)" :key="item.id">
                <img :src="'/assets/posts/' + item.title.replace(/[\s:;*?<>]+/g, '-').toLowerCase() + '/img/header.jpg'" :alt="item.title" class="w-[40px] h-[40px] rounded-full bg-pink-300">
                <div class="flex flex-col w-[220px] gap-1">
                    <p class="text-xs font-medium">{{ item.title }}.</p>
                    <p class="text-[10px]">{{ item.postDate }}</p>
                </div>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: "PostWidget",
    components: {},
    props: ['postData', 'data'],
    data() {
        return {
            title: '',
            myPosts: ''
        }
    },
    computed: {
    filteredItems() {
        return this.postData
            .filter(item => item.title !== this.data.name)
            .filter(item => item.category.some(cat => this.data.category.includes(cat)))
            .slice(-3)
        }
    },
    methods: {},
    mounted() {
        console.log(this.postData[1].title === this.data.name)
        if(this.data == 'recent') {
            this.title = 'Recent Post'
            this.myPosts = this.postData
        } else {
            this.title = 'Related Post'
            this.myPosts = this.filteredItems
        }
    }
}
</script>