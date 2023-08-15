<template>
 <NuxtLayout>
  <Header></Header>
    <div class="container grid grid-cols-3 md:grid-cols-12">
      <Sidebar></Sidebar>
    <main class="col-span-3 p-4 md:col-span-9 grid gap-4 m-8">
      <NuxtPage />
    </main>
  </div>
  <Footer></Footer>
 </NuxtLayout>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';
import Sidebar from './components/Sidebar';

export default {
  components: {
    Header,
    Footer,
    Sidebar,
  }
}
</script>
