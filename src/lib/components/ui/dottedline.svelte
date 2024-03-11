<script lang="ts">
  export let line: "large" | "small";
  import ArrowUp from "$lib/components/icons/arrowUp.svelte";
  let heights = {
    large: {
      lineHeight: 250,
      circle: 4,
    },
    small: {
      lineHeight: 150,
      circle: 8,
    },
  };
  let h = heights[line].lineHeight;
  let circle = heights[line].circle;
</script>

{#if line === "large"}
  <div class=" w-2 flex flex-col items-center gap-1">
    <div class="flex flex-col items-center">
      {#if line !== "large"}
        <ArrowUp />
      {/if}
      <div
        class="h-[125px] border-l-4 w-0 border-dotted border-slate-300"
      ></div>
    </div>
    <div class="w-4 h-4 border-4 rounded-full border-[#0066FF]"></div>
    <div class="h-[125px] border-l-4 w-0 border-dotted border-slate-300"></div>
  </div>
{:else}
  <div class=" w-2 flex flex-col items-center gap-1">
    <div class="flex flex-col items-center">
      <ArrowUp />
      <div class="h-[65px] border-l-4 w-0 border-dotted border-slate-300"></div>
    </div>
    <div class="w-8 h-8 border-8 rounded-full border-[#0066FF]"></div>
    <div class="h-[65px] border-l-4 w-0 border-dotted border-slate-300"></div>
  </div>
{/if}
