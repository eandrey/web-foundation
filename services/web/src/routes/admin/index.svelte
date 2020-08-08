<script>
    import {goto} from '@sapper/app'
    import {onMount} from 'svelte'
    import {currentUser} from '../../stores/user.js'
    import NewBlogPost from '../../components/new-blog-post.svelte'

    onMount(()=>{
        if(!currentUser){
            goto('/auth/login?redirect=admin')   
        }
    })
</script>

{#if $currentUser}
     <NewBlogPost />
{/if}
