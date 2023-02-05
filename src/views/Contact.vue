<template>
    <div id="contact" class="w-full h-[500px] px-12 pb-12 bg-[#050915] font-poppins flex flex-col items-center">
        <Navbar />
        <h1>Contact Page</h1>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';

export default {
    name: 'Contact',
    components: { Navbar }
}
</script>