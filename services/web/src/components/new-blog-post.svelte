<script>
  import Button from "./ui-elements/button.svelte";
  import InputGroup from "./ui-elements/input-group.svelte";

  let title;
  let content;

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
      errorMessage = "Please provide a title"
      hasError = {!title}
      bind:value={title} />
    <InputGroup
      elementType="textarea"
      label="Content"
      id="content"
      placeholder="Your content ..."
      errorMessage = "Please provide a content"
      hasError = {!content}
      bind:value={content} />
      <Button disabled={isPublishedDisabled}>Publish</Button>

  </form>
</div>
