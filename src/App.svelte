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

    const LATITUDE = -6.8220235;
    const LONGITUDE = 107.1786049;

    let mapUrl = `https://www.openstreetmap.org/export/embed.html?bbox=${LONGITUDE - 0.005},${LATITUDE - 0.005},${LONGITUDE + 0.005},${LATITUDE + 0.005}&layer=mapnik&marker=${LATITUDE}%2C${LONGITUDE}`;
</script>

<Header />

<main class="container mx-auto font-hanken-grotesk">
    <section class="py-20 px-10 lg:py-40 lg:px-20">
        <Headline category="Fitur" desc="Semua Kenyamanan dalam Satu Masjid" />

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 mt-10">
            {#each features as feature, i}
                <div
                    class="flex flex-col items-center justify-center text-center gap-4"
                >
                    <img
                        src={feature.imgPath}
                        alt={"Subtract-" + i}
                        class="object-cover w-16 lg:w-32"
                    />
                    <span class="font-medium text-sm lg:text-lg"
                        >{feature.label}</span
                    >
                </div>
            {/each}
        </div>
    </section>

    <section class="py-20 px-10 lg:py-40 lg:px-20 bg-primary lg:rounded-xl">
        <Headline
            type="white"
            category="Kegiatan"
            desc="Berbagai Kegiatan Menarik Yang Tersedia di Masjid"
        />

        <div
            class="flex flex-col lg:flex-row gap-10 items-center justify-center mt-10"
        >
            {#each activities as activity, i}
                <Card
                    title={activity.title}
                    description={activity.description}
                    imgPath={activity.imgPath}
                />
            {/each}
        </div>
    </section>

    <section class="py-20 px-10 lg:py-40 lg:px-20">
        <Headline
            category="Foto"
            desc="Menjelajahi Keindahan Masjid Dari Berbagai Sisi"
        />

        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-10">
            {#each Array(Math.ceil(photos.length / 2)) as _, colIndex}
                <div class="grid gap-4">
                    {#each photos.slice(colIndex * 2, colIndex * 2 + 2) as photo, i}
                        <div>
                            <img
                                class="h-auto max-w-full rounded-lg hover:scale-105 transition-all ease-in-out cursor-pointer hover:opacity-90"
                                src={photo}
                                alt=""
                            />
                        </div>
                    {/each}
                </div>
            {/each}
        </div>
    </section>

    <section class="py-20 px-10 lg:pb-40 lg:px-20">
        <Headline category="Lokasi" desc="Lokasi Masjid Mudah Diakses" />

        <div class="w-full h-[400px] mt-10">
            <iframe
                width="100%"
                height="100%"
                title="Lokasi"
                frameborder="0"
                style="border:0"
                src={mapUrl}
                allowfullscreen
            >
            </iframe>
        </div>
    </section>
</main>

<Footer />
