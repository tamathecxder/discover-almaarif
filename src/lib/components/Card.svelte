<script>
    let { title, description, imgPath } = $props();
</script>

<div class="flex flex-col gap-4 px-6 py-4 bg-beige min-h-[420px] rounded-xl">
    <div class="flex flex-col gap-4 max-w-72">
        <h4 class="line-clamp-3 font-extrabold text-3xl">{title}</h4>
        <p class="line-clamp-3 text-sm">{description}</p>
    </div>

    <img src={imgPath} alt={title} class="h-44 object-cover object-center rounded-lg">
</div>