<template>
    <header class="fixed top-0 right-0 left-0 bg-transparent container z-10 max-w-[1400px]">
        <div class="flex justify-between gap-10  h-[72px]  items-center text-white container">
            <div>
                <img src="../assets/logo-scrolled.png" alt="logo" />
            </div>
            <nav :class="`flex items-center gap-11 text-black font-semibold`">
                <router-link to="/">Tính năng</router-link> 
                <router-link to="/about">Giải pháp</router-link>
                <router-link to="/about">SMIT Gate là gì</router-link>
                <router-link to="/about">Bảng giá</router-link>
            </nav>
            <div>
                <button>Liên hệ</button>
            </div>
        </div>
    </header>
</template>
<script>
export default {
    name: 'Header',
    data() {
        return {
            isScrolled: false,
        }
    },
    computed: {
        getLogo() {
            return this.isScrolled ? '../assets/logo-scrolled.png' : '../assets/logo.png';
        }
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            if (window.scrollY > 0) {
                this.isScrolled = true;
            } else {
                this.isScrolled = false;
            }
        }
    }
}
</script