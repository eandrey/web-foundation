<script>
  import FeatureToggle from "../components/feature-toggle.svelte";
  import { FEATURE_TOGGLES } from "../feature-toggles";
<<<<<<< HEAD
  import Card from "../components/card.svelte"


	const imageSrc = 'https://habrastorage.org/getpro/habr/upload_files/a87/6a8/e95/a876a8e9579264bfc60373d04f3ff3c9.jpg'


=======
  import ContactCard from "../components/contact-card.svelte";

 
  const personData = {
    src: 'https://ph-files.imgix.net/c0538f37-136e-402c-9106-a0db7df60991.jpeg?auto=format&auto=compress&codec=mozjpeg&cs=strip&w=80&h=80&fit=crop&dpr=2',
    alt: 'image',
    job: "Customer Support",
    email: "e​rinlindford@example.com",
    phone: "(555) 765-4321",
    name: "Erin Lindford"
  }
  
>>>>>>> 11ef59e3852a5d9deb5b8c7a71f24a73f87a059f
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<h1>About this site</h1>


<Card {imageSrc}  />


<p>This is the 'about' page. There's not much here.</p>

<ContactCard data = {personData} {...personData}  />

<FeatureToggle name={FEATURE_TOGGLES.vipWelcome.name}>
  <p>Some people see this, others don't!</p>
</FeatureToggle>
