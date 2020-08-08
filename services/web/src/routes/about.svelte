<script>
  import FeatureToggle from "../components/feature-toggle.svelte";
  import { FEATURE_TOGGLES } from "../feature-toggles";
  import ContactCard from "../components/contact-card.svelte";

 
  const personData = {
    src: 'https://ph-files.imgix.net/c0538f37-136e-402c-9106-a0db7df60991.jpeg?auto=format&auto=compress&codec=mozjpeg&cs=strip&w=80&h=80&fit=crop&dpr=2',
    alt: 'image',
    job: "Customer Support",
    email: "e​rinlindford@example.com",
    phone: "(555) 765-4321",
    name: "Erin Lindford"
  }
  
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<h1>About this site</h1>

<p>This is the 'about' page. There's not much here.</p>

<ContactCard data = {personData} {...personData}  />

<FeatureToggle name={FEATURE_TOGGLES.vipWelcome.name}>
  <p>Some people see this, others don't!</p>
</FeatureToggle>
