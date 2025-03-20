<script>
    let { brandLogo, menuItems, isHamburgerOpen } = $props();
</script>

<div
    class="hidden lg:flex relative container mx-auto z-20 py-10 px-20 items-center justify-between"
>
    <img
        src={brandLogo}
        alt="Brand Logo"
        class="h-10 object-center object-cover -mt-4 cursor-pointer"
    />
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

<div
    class="{isHamburgerOpen
        ? 'block lg:hidden translate-y-0'
        : 'hidden -translate-y-5'} 
           bg-white/90 fixed w-full mx-auto z-[9998] py-6 px-4 rounded-lg shadow-lg transition-all duration-300 ease-in-out transform"
>
    <nav>
        <ul class="flex flex-col gap-4 text-primary">
            {#each menuItems as item}
                <li
                    class="cursor-pointer hover:text-teal-500 transition-colors duration-200"
                >
                    {item}
                </li>
            {/each}
        </ul>
    </nav>
</div>
