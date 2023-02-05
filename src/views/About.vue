<template>
    <div id="about" class="w-full h-[500px] px-12 pb-12 bg-[#050915] font-poppins flex flex-col items-center">
        <Navbar />
        <h1>About Page</h1>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
export default {
    name: 'About',
    components: {
        Navbar
    }
}
</script>