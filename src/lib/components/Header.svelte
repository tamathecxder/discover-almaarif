<script lang="ts">
    const brandLogo = 'assets/brand-logo.png';
    const menuItems: string[] = ['Beranda', 'Blog', 'Kegiatan', 'Tentang', 'Kontak'];
</script>

<header class="container mx-auto z-20 absolute py-10 px-20 flex items-center justify-between">
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
</header>