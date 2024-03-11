<script>
  import Button from "$lib/components/ui/button/button.svelte";
  import Logo from "$lib/components/icons/logo.svelte";
  import LinkExternal from "$lib/components/icons/linkExternal.svelte";
  import Dots from "$lib/components/icons/dots.svelte";
  import * as AlertDialog from "$lib/components/ui/alert-dialog";

  let followed = true;

  function onFollow() {
    followed = !followed;
  }
</script>

<section class="flex justify-between gap-8 px-32">
  <div class="flex flex-col items-center justify-center">
    <img
      src="/hero.png"
      alt="profile "
      class="rounded-full w-64 aspect-square border-4 border-slate-200"
    />
    <h2 class="text-2xl font-bold text-center text-[#4B5C6D]">Krishna Kiran</h2>
  </div>

  <div class="flex flex-col justify-between py-4 gap-4">
    <div class="flex justify-between">
      <p class="text-wrap w-3/5 text-base font-normal">
        Co-Founder and CEO at Duggup - Social network for people in tech.
        Ex-Amazon Head of Engineering. I write hot-takes on building a business,
        shipping delightful products and accelerating product and career growth.
      </p>

      <div class="flex flex-col items-end gap-1">
        <Logo />
        <h2 class="text-lg font-bold">Duggup</h2>
        <p class="text-sm font-normal text-slate-400">Co-Founder and CEO</p>
      </div>
    </div>

    <div class="flex justify-between">
      {#if followed}
        <Button
          on:click={onFollow}
          variant="outline"
          class="px-8 py-5 border border-b-4 border-slate-400 hover:bg-[#0066FF] hover:text-white hover:border-b-blue-900"
          >Follow
        </Button>
      {:else}
        <AlertDialog.Root>
          <AlertDialog.Trigger>
            <Button
              variant="outline"
              class="px-8 py-5 border border-b-4 border-slate-400 hover:text-red-600 hover:border-red-700 hover:border-b-red-900"
              >Following
            </Button>
          </AlertDialog.Trigger>
          <AlertDialog.Content>
            <AlertDialog.Header>
              <AlertDialog.Title>Are you absolutely sure?</AlertDialog.Title>
            </AlertDialog.Header>
            <AlertDialog.Footer>
              <AlertDialog.Cancel>Cancel</AlertDialog.Cancel>
              <AlertDialog.Action on:click={onFollow}
                >Unfollow</AlertDialog.Action
              >
            </AlertDialog.Footer>
          </AlertDialog.Content>
        </AlertDialog.Root>
      {/if}
      <div class="flex items-center">
        <Button
          target="_blank"
          href="https://techspaceblogs.netlify.app"
          variant="link"
          class="flex items-center cursor-pointer "
        >
          <p class="text-slate-700 font-normal text-base">My website</p>
          <LinkExternal />
        </Button>
        <Dots />
      </div>
    </div>
  </div>
</section>
