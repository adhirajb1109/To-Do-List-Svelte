<script>
  import Navbar from "./Navbar.svelte";
  import ToDo from "./To-Do.svelte";
  import AddToDo from "./AddToDo.svelte";
  let todos = [
    {
      title: "Play Guitar",
      description: "Play Guitar",
    },
    {
      title: "Read Books",
      description: "Read Books",
    },
    {
      title: "Go To Gym",
      description: "Go To Gym",
    },
  ];
  const addtodo = (e) => {
    const newtodo = e.detail;
    todos = [...todos, newtodo];
  };
  const removetodo = (e) => {
    todos = todos.filter((todo) => todo.title !== e.detail);
  };
</script>

<Navbar />
<div class="container">
  <AddToDo on:addtodo={addtodo} />
  {#if todos.length === 0}
    {""}
  {:else}
    {#each todos as todo}
      <ToDo
        title={todo.title}
        description={todo.description}
        on:removetodo={removetodo}
      />
    {/each}
  {/if}
</div>
