<script>
    const items = [
        {
            title: "Halaman",
            children: ["Beranda", "Blog", "Kegiatan", "Tentang", "Kontak"],
        },
        {
            title: "Kegiatan",
            children: [
                "Kajian Fiqih",
                "Kajian Ibadah 4 Madzhab",
                "Santunan Dhuafa",
                "Pelatihan Kewirausahaan",
                "Belajar Ngaji",
            ],
        },
        {
            title: "Kontak",
            children: [
                "081234567890 (WA)",
                "987F1D6L (PIN BBM)",
                "087634561234 (Telegram)",
            ],
        },
    ];

    const copyright = "© 2024 Masjid Al-Kandari All Rights Reserved";
</script>

<footer
    class="flex flex-col justify-center items-center bg-primary text-beige pt-20 pb-10 px-10 lg:px-20 font-hanken-grotesk"
>
    <div
        class="container flex flex-col lg:flex-row items-start justify-start gap-10 lg:gap-60 w-full"
    >
        <!-- Left -->
        <div class="flex flex-col gap-6 items-start">
            <img
                src="assets/brand-logo.png"
                alt="Brand Logo"
                class="h-10 object-center object-cover"
            />
            <p class="max-w-xs text-sm">
                Masjid ini memiliki desain arsitektur indah dan fasilitas
                lengkap, menyediakan lingkungan yang nyaman untuk ibadah dan
                kegiatan komunitas.
            </p>

            <div class="flex flex-row gap-4">
                <div
                    class="rounded-full bg-beige text-black w-10 h-10 flex items-center justify-center cursor-pointer hover:bg-blue-200"
                >
                    <img src="assets/fb-outline.svg" alt="FB" class="w-4 h-4" />
                </div>
                <div
                    class="rounded-full bg-beige text-black w-10 h-10 flex items-center justify-center cursor-pointer hover:bg-blue-200"
                >
                    <img src="assets/ig-outline.svg" alt="FB" class="w-4 h-4" />
                </div>
                <div
                    class="rounded-full bg-beige text-black w-10 h-10 flex items-center justify-center cursor-pointer hover:bg-blue-200"
                >
                    <img
                        src="assets/tiktok-outline.svg"
                        alt="FB"
                        class="w-4 h-4"
                    />
                </div>
            </div>
        </div>

        <!-- Right -->
        <div class="flex flex-col lg:flex-row gap-10 lg:gap-[120px]">
            {#each items as item}
                <div class="flex flex-col gap-4">
                    <h5 class="font-extrabold text-base">{item.title}</h5>
                    <ul>
                        {#each item.children as child}
                            <li
                                class="cursor-pointer text-sm font-normal mb-4 hover:text-blue-200"
                            >
                                {child}
                            </li>
                        {/each}
                    </ul>
                </div>
            {/each}
        </div>
    </div>

    <p class="mt-10 lg:mt-20 text-sm">{copyright}</p>
</footer>
