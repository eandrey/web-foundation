<script>
  import { onMount } from "svelte";
  import { currentUser } from "../stores/user.js";
  import { goto, stores} from "@sapper/app"

  const {page} = stores()

  onMount(() => {
    firebase.auth().onAuthStateChanged(user => {
    //   user ? currentUser.signIn(user) : currentUser.signOut();
        if(user) {
            currentUser.signIn(user);
                if($page.query.redirect){
                    goto($page.query.redirect)
                }
        }else{
            currentUser.signOut()
        }
    });
  });
</script>
