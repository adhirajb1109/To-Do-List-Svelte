<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let title;
  export let description;
  const onDelete = () => dispatch("removetodo", title);
</script>

<div class="card">
  <h1>
    {title}
  </h1>
  <h3>{description}</h3>
  <button class="btn btn-danger" on:click={onDelete}>Delete</button>
</div>

<style>
  h1 {
    color: #204f6e;
  }
  h3 {
    margin-bottom: 10px;
  }
  button {
    margin-top:10px;
  }
</style>
