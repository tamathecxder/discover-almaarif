<script lang="ts">
  let { 
    type = "fill", 
    text, 
    icon = null } = $props();
</script>

<button
  class="flex items-center gap-2 cursor-pointer rounded-md px-10 py-3 text-sm {type === 'fill'
    ? 'bg-white text-black hover:opacity-90'
    : 'border border-white hover:bg-overlay/100'}">
    {#if icon}
        <img src={icon} alt="Icon" class="w-4 h-4">
    {/if}
    <span>{text}</span>
</button>
