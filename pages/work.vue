<template>
  <div class="bg-black h-screen px-6 py-12">
    <h1
      class="text-white font-exo text-5xl opacity-0 pb-5"
      ref="title"
      style="transform: translateY(30px)"
    >
      MY WORK
    </h1>
    <div class="flex space-x-4">
      <div
        v-for="project in projects"
        class="w-full opacity-0"
        ref="projects"
        style="transform: translateX(30px)"
      >
        <nuxt-link to="/">
          <img
            :src="project.image.url"
            alt="1"
            class="object-cover"
            style="height: 70vh"
          />
          <p class="text-white font-spaceMono text-sm">{{ project.title }}</p>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import iphoneImg1 from '../images/1.jpg'
import iphoneImg2 from '../images/2.jpg'
import iphoneImg3 from '../images/3.jpg'
import iphoneImg4 from '../images/4.jpg'
import iphoneImg5 from '../images/5.jpg'
import iphoneImg6 from '../images/2.jpg'
import gsap from 'gsap'
export default {
  data() {
    return {
      projects: [
        {
          image: {
            url: iphoneImg1,
          },
          title: 'iMac',
        },
        {
          image: {
            url: iphoneImg2,
          },
          title: 'iMac',
        },
        {
          image: {
            url: iphoneImg3,
          },
          title: 'iPhone',
        },
        {
          image: {
            url: iphoneImg4,
          },
          title: 'iMac',
        },
        {
          image: {
            url: iphoneImg5,
          },
          title: 'Robot',
        },
        {
          image: {
            url: iphoneImg6,
          },
          title: 'iMac',
        },
      ],
    }
  },

  mounted() {
    gsap.to(this.$refs.title, {
      opacity: 1,
      duration: 1.5,
      y: 0,
      ease: 'expo',
    })
    gsap.to(this.$refs.projects, {
      opacity: 1,
      duration: 1.5,
      stagger: 0.3,
      x: 0,
      ease: 'expo',
      delay: 0.5,
    })
  },
}
</script>

<style>
.font-exo {
  font-family: 'Exo 2', sans-serif;
}

.font-spaceMono {
  font-family: 'Space Mono', monospace;
}
</style>
