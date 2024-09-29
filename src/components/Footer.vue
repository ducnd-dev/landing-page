<template>
    <footer class=" text-white p-14 text-center">
        <div class="flex gap-5 justify-center">
            <a v-for="social in socials" :key="social.name" :href="social.link" class="inline-block ">
                <img :src="social.icon" :alt="social.name" />
            </a>
        </div>
        <div class="text-black">
            <h2 class="font-semibold text-3xl my-3">Join the adventure</h2>
            <p>Become part of the lempire journey and work alongside <br > passionate people who love to get things done.</p>
        </div>
    </footer>
</template>

<script>
import note from '../assets/note-2.svg';
export default {
    name: 'Footer',
    data() {
        return {
            socials: [
                {
                    name: 'Facebook',
                    link: '',
                    icon: note,
                },
                {
                    name: 'Twitter',
                    link: '',
                    icon: note,
                },
                {
                    name: 'Twitter',
                    link: '',
                    icon: note,
                },
                {
                    name: 'Twitter',
                    link: '',
                    icon: note,
                },
                {
                    name: 'Twitter',
                    link: '',
                    icon: note,
                },
            ],
        }
    }
}     
</script>