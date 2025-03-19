<script>
    let { type = "default", category, desc } = $props();
</script>

<div class="flex flex-col items-center font-hanken-grotesk text-center">
    <span
        class="uppercase text-base lg:text-lg font-bold mb-2 {type === 'default'
            ? 'text-primary'
            : 'text-beige'}">{category}</span
    >
    <h3
        class="text-3xl lg:text-5xl max-w-2xl font-extrabold leading-tight {type ===
        'default'
            ? 'text-black'
            : 'text-beige'}"
    >
        {desc}
    </h3>
</div>
