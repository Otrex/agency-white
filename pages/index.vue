<template> 
  <div> 
    <Head> 
      <Title>Agency Page - White</Title>
      <Meta content="page" />
    </Head>

    <main class="overflow-y-scroll"> 
      <NavBar :data="data" />
      <Hero :data="data" />
      <Consultation :data="data" />
      <Help :data="data" />
      <Services :data="data" /> 
      <Benefits :data="data" /> 
      <About :data="data" />
      <Testimonials :data="data" />
      <XFooter :data="data" />
    </main>
    
  </div>
</template>

<script setup lang="ts">
import { WizardResponse } from '~/type';

 
const route = useRoute();
const data = ref<WizardResponse>();

onBeforeMount(async () => {
  console.log(window.location);
  
})
</script>
