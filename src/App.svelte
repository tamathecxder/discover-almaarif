<script lang="ts">
  import Card from "./lib/components/Card.svelte";
  import Footer from "./lib/components/Footer.svelte";
  import Header from "./lib/components/Header.svelte";
  import Headline from "./lib/components/Headline.svelte";
  import type { Activity } from "./lib/interfaces/Activity";
  import type { Feature } from "./lib/interfaces/Feature";

  const features: Feature[] = [];
  const activities: Activity[] = [
    {
      title: "Kajian Fiqih, Kajian Ibadah 4 Madzhab dan Belajar Ngaji",
      description:
        "Di setiap harinya, masjid akan melaksanakan banyak kegiatan keislaman, terbuka untuk masyarakat sekitar dan untuk umum.",
      imgPath: "assets/act-1.png",
    },
    {
      title: "Sembako Gratis dan Santunan Terhadap Dhuafa",
      description:
        "Tersedia paket sembako gratis dan juga rutin melaksanakan kegiatan santunan terhadap dhuafa.",
      imgPath: "assets/act-2.png",
    },
    {
      title: "Pendidikan dan Pelatihan Kewirausahaan",
      description:
        "Masjid rutin membina jama’ah di segala usia agar memiliki keterampilan dan minat belajar yang tinggi demi masa depan yang cerah.",
      imgPath: "assets/act-3.png",
    },
  ];
  const photos: string[] = [];

  const labels: string[] = [
    "Imam Hafidz Qur'an dan Menguasai Berbagai Nagham",
    "Masjid Dilengkapi AC, Memastikan Ruangan Sejuk",
    "Masjid Terbuka 24 Jam dengan Jaminan Keamanan",
    "Menggunakan Karpet Terbaik yang Lembut Dipakai Sujud",
  ];

  [1, 2, 3, 4].forEach((num) => {
    features.push({
      imgPath: `assets/Subtract-${num}.svg`,
      label: labels[num - 1],
    });
  });

  [1, 2, 3, 4, 5, 6, 7, 8].forEach((num) => {
    photos.push(`assets/photo_${num}.jpg`);
  });
</script>

<Header />

<main class="container mx-auto font-hanken-grotesk">
  <section class="py-40 px-20">
    <Headline category="Fitur" desc="Semua Kenyamanan dalam Satu Masjid" />

    <div class="flex flex-row gap-4 items-center justify-center mt-10">
      {#each features as feature, i}
        <div
          class="flex flex-col gap-4 text-center items-center justify-center"
        >
          <img
            src={feature.imgPath}
            alt={"Subtract-" + i}
            class="object-cover w-32"
          />
          <span class="font-medium text-lg">{feature.label}</span>
        </div>
      {/each}
    </div>
  </section>

  <section class="py-40 px-20 bg-primary rounded-xl">
    <Headline
      type="white"
      category="Kegiatan"
      desc="Berbagai Kegiatan Menarik Yang Tersedia di Masjid"
    />

    <div class="flex flex-row gap-10 items-center justify-center mt-10">
      {#each activities as activity, i}
        <Card
          title={activity.title}
          description={activity.description}
          imgPath={activity.imgPath}
        />
      {/each}
    </div>
  </section>

  <section class="py-40 px-20">
    <Headline
      category="Foto"
      desc="Menjelajahi Keindahan Masjid Dari Berbagai Sisi"
    />

    <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-10">
      {#each Array(Math.ceil(photos.length / 2)) as _, colIndex}
        <div class="grid gap-4">
          {#each photos.slice(colIndex * 2, colIndex * 2 + 2) as photo, i}
            <div>
              <img class="h-auto max-w-full rounded-lg" src={photo} alt="" />
            </div>
          {/each}
        </div>
      {/each}
    </div>
  </section>
</main>

<Footer />
