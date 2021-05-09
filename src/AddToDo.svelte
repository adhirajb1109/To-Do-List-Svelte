<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  let todo = {
    title: "",
    description: "",
  };
  const onSubmit = (e) => {
    e.preventDefault();
    dispatch("addtodo", todo);
    todo = {
    title: "",
    description: "",
    };
  };
</script>

<form on:submit={onSubmit} class="grid-3">
  <input type="text" placeholder="Enter Task Title :" bind:value={todo.title} />
  <input type="text" placeholder="Enter Task Description :" bind:value={todo.description} />
  <input type="submit" class="btn btn-primary" value="Add Task" />
</form>
