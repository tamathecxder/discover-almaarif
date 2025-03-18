<script>
    let { type = 'default', category, desc } = $props(); 
</script>

<div class="flex flex-col items-center font-hanken-grotesk text-center">
    <span class="uppercase text-lg font-bold mb-2 {type === 'default' ? 'text-primary' : 'text-white'}">{category}</span>
    <h3 class="text-5xl max-w-2xl font-extrabold leading-tight {type === 'default' ? 'text-black' : 'text-white'}">{desc}</h3>
</div>