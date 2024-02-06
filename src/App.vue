<template>
  <MainHeader/>
  <HeroSection />
  <MenuSection/>
</template>
<script>
import MainHeader from './components/MainHeader.vue'
import HeroSection from './components/HeroSection.vue'
import MenuSection from './components/MenuSection.vue'
export default {
  name: 'App',
  components: {
    MainHeader,
    HeroSection,
    MenuSection
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');
body{
  font-family: 'Poppins', sans-serif;
  background-color: #19161B;
  color: #fff;
}
</style>