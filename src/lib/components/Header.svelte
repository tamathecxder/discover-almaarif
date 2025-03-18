<script lang="ts">
    import Button from "./Button.svelte";
    
    const brandLogo = 'assets/brand-logo.png';
    const menuItems: string[] = ['Beranda', 'Blog', 'Kegiatan', 'Tentang', 'Kontak'];
</script>

<header class="relative h-[810px] bg-[url('assets/hero-overlay.png')] bg-center bg-cover bg-no-repeat">
    <div class="mix-blend-multiply absolute inset-0 bg-overlay/90 z-10"></div>
    
    <div class="relative container mx-auto z-20 py-10 px-20 flex items-center justify-between">
        <img src={brandLogo} alt="Brand Logo" class="h-10 object-center object-cover -mt-4 cursor-pointer">
        <nav>
            <ul class="flex gap-10 text-white">
                {#each menuItems as item}
                    <li class="cursor-pointer hover:text-teal-200">
                        {item}
                    </li>
                {/each}
            </ul>
        </nav>
    </div>

    <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 container mx-auto z-20 py-10 px-20 flex flex-col items-center gap-8 text-white text-center">
        <h1 class="text-6xl font-extrabold max-w-4xl tracking-wide">Temukan kedamaian melalui dekat dengan Tuhan</h1>
        <p class="text-lg max-w-2xl">
            Masjid bukan hanya sebagai tempat ibadah yang nyaman, tapi juga jadi tempat berbagai kegiatan, memupuk persaudaraan hingga membangkitkan perekonomian, atau tempat apapun yang berkaitan dengan keumatan.
        </p>

        <div class="flex flex-col lg:flex-row gap-4">
            <Button text="Baca Selengkapnya" type="outline" />
            <Button text="Hubungi Kami" icon="assets/wa-logo-outline.svg" />
        </div>
    </div>
</header>
