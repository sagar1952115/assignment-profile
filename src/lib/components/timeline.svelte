<script>
  import Blogcard from "./ui/blogcard.svelte";
  import Dottedline from "./ui/dottedline.svelte";

  let timelineData = [
    {
      type: "blog",
      date: "Dec 2023",
      blogs: [
        {
          img: "/stevejobs.png",
          title:
            "No amount of technology can convert a bad story into a good story",
        },
        {
          img: "/sam.png",
          title:
            "Most people don't have original ideas. Here is how Sam Altman pushes himself to have unpopular ideas",
        },
      ],
    },
    {
      type: "company",
      data: {
        logo: "/duggup.png",
        address: "San Francisco Bay Area",
        joined: "Nov 2023",
        title: "Co-Founder and CEO",
        type: "Full-time Remote",
        name: "Duggup",
      },
      blogs: [],
    },
    {
      type: "blog",
      date: "Oct 2023",
      blogs: [
        {
          img: "/computer.png",
          title: `Startup Lesson I am reflecting. Don't build for the "average person"`,
        },
        {
          img: "/map.png",
          title: "Your biggest regrets at 80 will be acts of omission",
        },
      ],
    },
    {
      type: "company",
      data: {
        logo: "betterup.png",
        address: "San Francisco Bay Area",
        joined: "Sep 2022",
        title: "VP Engineering",
        type: "Full-time",
        name: "BetterUp",
      },
      blogs: [],
    },
  ];
</script>

<section class="my-12 flex flex-col gap-3">
  {#each timelineData as data}
    {#if data.type === "blog"}
      <div class="flex items-center gap-8 px-24">
        <p class="text-slate-600 text-sm font-normal">{data.date}</p>

        <Dottedline line={"large"} />

        <div class="flex justify-center gap-12 mx-4">
          {#each data.blogs as blog}
            <Blogcard data={blog} />
          {/each}
        </div>
      </div>
    {:else}
      <div class="flex gap-8 px-1 py-2">
        <div class="flex flex-col items-end">
          <img src={data.data?.logo} alt="" class="w-10 h-10 my-2" />
          <h3 class="text-base font-bold">{data.data?.name}</h3>
          <p class="text-sm font-normal text-slate-500">{data.data?.address}</p>
          <p class="text-sm font-normal text-slate-500">Joined</p>
          <p class="text-sm font-normal text-slate-500">{data.data?.joined}</p>
        </div>
        <Dottedline line={"small"} />
        <div class="flex flex-col justify-center mx-4">
          <h2 class="font-bold text-xl">{data.data?.title}</h2>
          <p class="font-normal text-sm text-slate-500">{data.data?.type}</p>
        </div>
      </div>
    {/if}
  {/each}
</section>
