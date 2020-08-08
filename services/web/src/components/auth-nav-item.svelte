<script>
  import { currentUser } from "../stores/user.js";

  function signOut(){
      firebase.auth().signOut()
  }
</script>

<style>
  a {
    /* Matches the styles in Nav.svelte */
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

{#if $currentUser}
  <a href on:click={signOut}>Sign Out</a>
{:else}
  <a href="/auth/login">Sign In</a>
{/if}
