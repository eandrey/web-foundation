<script>
  import { onMount } from "svelte";
  import { currentUser } from "../stores/user.js";

  onMount(() => {
    firebase.auth().onAuthStateChanged(user => {
      user ? currentUser.signIn(user) : currentUser.signOut();
    });
  });
</script>
