<script lang="ts">
  import Card from "./ui-library/card/card.svelte";
  import type { FeatureTitle as FeatureTitleProps } from "$lib/types/feature-title";

  export let featureTitle: FeatureTitleProps;
  export let featureTitlePadding: string;
  const { main, sub, third, swap, showLeftKumquat, showRightKumquat } =
    featureTitle;
</script>

<Card
  size="small"
  class="w-full sm:w-[296px] {featureTitlePadding} text-center"
>
  {#if showLeftKumquat}
    <img
      src="/images/startups/kumquat-right.png"
      alt="Gitpod Kumquat"
      class="absolute hidden -z-10 md:block -left-[44px] -top-[16px] lgx:top-[-30px] lgx:left-[-86px] h-16 lgx:h-32 lgx:w-36"
    />
  {/if}
  {#if showRightKumquat}
    <img
      src="/images/startups/kumquat-left.png"
      alt="Gitpod Kumquat"
      class="absolute hidden -z-10 md:block top-[110px] lgx:top-[82px] right-[-60px] lgx:right-[-112px] h-16 lgx:h-32 lgx:w-36"
    />
  {/if}
  <h2 class="h2 !mb-0">
    <div class={swap ? "text-medium font-normal text-body" : ""}>
      {main}
    </div>
    <div
      class="{!swap
        ? 'text-medium font-normal text-body'
        : ''} mt-macro sm:mt-micro"
    >
      {sub}
    </div>
    {#if third}
      <div class="text-medium font-normal text-body">
        {third}
      </div>
    {/if}
  </h2>
</Card>
