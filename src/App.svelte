<script lang="ts">
  import Footer from "./lib/components/Footer.svelte";
  import Header from "./lib/components/Header.svelte";
  import Headline from "./lib/components/Headline.svelte";
  import type { Feature } from "./lib/interfaces/Feature";

  const features: Feature[] = [];
  const labels: string[] = [
    'Imam Hafidz Qur\'an dan Menguasai Berbagai Nagham',
    'Masjid Dilengkapi AC, Memastikan Ruangan Sejuk',
    'Masjid Terbuka 24 Jam dengan Jaminan Keamanan',
    'Menggunakan Karpet Terbaik yang Lembut Dipakai Sujud'
  ];
  
  [1,2,3,4].forEach((num) => {
    features.push({
      imgPath: `assets/Subtract-${num}.svg`,
      label: labels[num - 1],
    });
  });
</script>

<Header />

<main class="container mx-auto font-hanken-grotesk">
  <section class="py-40 px-20">
    <Headline category="Fitur" desc="Semua Kenyamanan dalam Satu Masjid" />

    <div class="flex flex-row gap-4 items-center justify-center mt-10">
      {#each features as feature, i}
        <div class="flex flex-col gap-4 text-center items-center justify-center">
          <img src={feature.imgPath} alt={'Subtract-' + i} class="object-cover w-32">
          <span class="font-medium text-lg">{feature.label}</span>
        </div>
      {/each}
    </div>
  </section>

  <section class="py-40 px-20 bg-primary rounded-xl">
    <Headline type="white" category="Kegiatan" desc="Berbagai Kegiatan Menarik Yang Tersedia di Masjid" />

    <div class="flex flex-row gap-4 items-center justify-center mt-10">
      {#each features as feature, i}
        <div class="flex flex-col gap-4 text-center items-center justify-center">
          <img src={feature.imgPath} alt={'Subtract-' + i} class="object-cover w-32">
          <span class="font-medium text-lg">{feature.label}</span>
        </div>
      {/each}
    </div>
  </section>
</main>

<Footer />
