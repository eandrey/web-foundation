<script>
  import Button from "./ui-elements/button.svelte";
  import InputGroup from "./ui-elements/input-group.svelte";

  let title;
  let content;

  let successMessage;
  let errorMessage;

  function publish() {
    const slug = title.replace(/\s/g, "-").toLowerCase();
    window.db
      .collection("posts")
      .doc(slug)
      .set({
        title,
        content
      })
      .then(() => {
        // console.log("Success");
        successMessage = "Successfully published your post";
      })
      .catch(err => {
        // console.log("Error", err);
        errorMessage = "Oh no... there was an error publishing";
      });
  }
  $: isPublishedDisabled = !(title && content);
</script>

<h1>Add new blog post</h1>
<div class="mt-6">
  <form>
    <InputGroup
      elementType="input"
      label="Title"
      id="title"
      placeholder="Untitled"
      errorMessage="Please provide a title"
      hasError={!title}
      bind:value={title} />
    <InputGroup
      elementType="textarea"
      label="Content"
      id="content"
      placeholder="Your content ..."
      errorMessage="Please provide a content"
      hasError={!content}
      bind:value={content} />
    <Button on:click={publish} disabled={isPublishedDisabled}>Publish</Button>

  </form>
  {#if successMessage}
    <p class="mt-2 text-sm">{successMessage}</p>
  {:else if errorMessage}
    <p class="mt-2 text-sm text-red-600">{errorMessage}</p>
  {/if}
</div>
