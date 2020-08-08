<script>
    import {goto} from '@sapper/app'
    import {onMount} from 'svelte'
    import {currentUser} from '../../stores/user.js'

    onMount(()=>{
        if(!currentUser){
            goto('/auth/login?redirect=admin')   
        }
    })
</script>

{#if $currentUser}
     <h1>Admin panel</h1>
      <p>Only authenticated users have access to this page</p>
{/if}
