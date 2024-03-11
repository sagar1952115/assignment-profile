<script lang="ts">
  import * as Card from "$lib/components/ui/card";
  import { AspectRatio } from "$lib/components/ui/aspect-ratio";

  export let data: { img: string; title: string };
</script>

<Card.Root class="cursor-pointer w-[344px]">
  <AspectRatio ratio={16 / 11}>
    <Card.Content class="w-full bg-red-50 p-0">
      <img src={data.img} alt="blog thumbnail" />
    </Card.Content>
    <Card.Footer class="px-4 py-6">
      <Card.Title class="font-normal text-left text-base text-wrap text-black p-0 line-clamp-2"
        >{data.title}.</Card.Title
      >
    </Card.Footer>
  </AspectRatio>
</Card.Root>
