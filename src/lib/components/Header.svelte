<script lang="ts">
    import Button from "./Button.svelte";
    import Navbar from "./Navbar.svelte";

    let isHamburgerOpen = $state(false);

    function toggle() {
        isHamburgerOpen = !isHamburgerOpen;
        console.log("isHamburgerOpen", isHamburgerOpen);
    }

    const brandLogo = "assets/brand-logo.png";
    const menuItems: string[] = [
        "Beranda",
        "Blog",
        "Kegiatan",
        "Tentang",
        "Kontak",
    ];
</script>

<header
    class="relative h-[810px] bg-[url('/assets/hero-overlay.png')] bg-center bg-cover bg-no-repeat"
>
    <div class="mix-blend-multiply absolute inset-0 bg-primary/90 z-10"></div>

    <button
        data-collapse-toggle="navbar-hamburger"
        type="button"
        class="lg:hidden bg-white fixed top-0 right-0 z-[9999] inline-flex items-center justify-center p-2 m-4 text-sm text-gray-500 rounded-lg hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
        aria-controls="navbar-hamburger"
        aria-expanded="false"
        onclick={toggle}
    >
        <span class="sr-only">Open main menu</span>
        <svg
            class="w-5 h-5"
            aria-hidden="true"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 17 14"
        >
            <path
                stroke="#000"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M1 1h15M1 7h15M1 13h15"
            />
        </svg>
    </button>

    <Navbar {isHamburgerOpen} {brandLogo} {menuItems} />

    <div
        class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 container mx-auto z-20 py-10 px-10 lg:px-20 flex flex-col items-center gap-8 text-white text-center"
    >
        <h1 class="text-4xl lg:text-6xl font-extrabold max-w-4xl tracking-wide">
            Temukan kedamaian melalui dekat dengan Tuhan
        </h1>
        <p class="text-sm lg:text-lg max-w-xl lg:max-w-2xl">
            Masjid bukan hanya sebagai tempat ibadah yang nyaman, tapi juga jadi
            tempat berbagai kegiatan, memupuk persaudaraan hingga membangkitkan
            perekonomian, atau tempat apapun yang berkaitan dengan keumatan.
        </p>

        <div class="flex flex-col lg:flex-row gap-4">
            <Button text="Baca Selengkapnya" type="outline" />
            <Button text="Hubungi Kami" icon="assets/wa-logo-outline.svg" />
        </div>
    </div>
</header>
