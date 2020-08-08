<script>
  import FeatureToggle from "../components/feature-toggle.svelte";
  import { FEATURE_TOGGLES } from "../feature-toggles";
  import Card from "../components/card.svelte"


	const imageSrc = 'https://habrastorage.org/getpro/habr/upload_files/a87/6a8/e95/a876a8e9579264bfc60373d04f3ff3c9.jpg'


</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<h1>About this site</h1>


<Card {imageSrc}  />


<p>This is the 'about' page. There's not much here.</p>

<FeatureToggle name={FEATURE_TOGGLES.vipWelcome.name}>
  <p>Some people see this, others don't!</p>
</FeatureToggle>
