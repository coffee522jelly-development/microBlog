<template>
 <NuxtLayout>
  <Header></Header>
    <div class="sm:m-32 m-8">
      <NuxtPage />
    </div>
  <Footer></Footer>
 </NuxtLayout>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';

export default {
  components: {
    Header,
    Footer,
  }
}
</script>
