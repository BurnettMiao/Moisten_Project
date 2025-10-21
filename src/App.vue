<script setup>
import Navbar from '@/components/Navbar.vue'
import HeroSection from '@/components/HeroSection.vue'
import MobileVideo from '@/components/MobileVideo.vue'
import IntroduceSection from '@/components/IntroduceSection.vue'
import OurGoalsSection from '@/components/OurGoalsSection.vue'
import EventRecord from '@/components/EventRecord.vue'
import StoreSection from '@/components/StoreSection.vue'
import QASection from '@/components/QASection.vue'
import Footer from '@/components/Footer.vue'
import GoToTop from '@/components/utility/GoToTop.vue'
</script>

<template>
  <div class="overflow-hidden">
    <Navbar />
    <HeroSection />
    <MobileVideo />
    <IntroduceSection />
    <OurGoalsSection />
    <EventRecord />
    <StoreSection />
    <QASection />
    <Footer />
    <GoToTop />
  </div>
</template>

<style scoped></style>
