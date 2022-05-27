<script>
  let todos = [];
  const addtodos = () => {
    todos = [...todos, ""];
  };
  const remove = (index) => {
    todos = [...todos.slice(0, index), ...todos.slice(index + 1)];
  };
  export let project;
</script>

<div class="container">
  <h1>{project}</h1>
  {#each todos as todo, index}
    <input bind:value={todos[index]} />
    <button class="button" on:click={() => remove(index)}>X</button>
    <br />
  {/each}
  <div class="btn" >
  <button class="button" on:click={addtodos}>Add</button>
</div>
</div>

<style>

  .container {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    border: 5px solid #65e0c8;
    padding: 10px;
  }
  input{
      margin: 10px;
  }
  h1 {
    text-align: center;
    color: #65e0c8;
  }
  .btn{
     width: 100%;
     display: flex;
     justify-content: center;
  }


.button {
  align-items: center;
  background: #FFFFFF;
  border: 0 solid #E2E8F0;
  box-sizing: border-box;
  color: #1A202C;
  display: inline-flex;
  font-family: Inter, sans-serif;
  font-size: 1rem;
  font-weight: 700;
  height: 28px;
  justify-content: center;
  line-height: 24px;
  overflow-wrap: break-word;
  padding: 16px;
  text-decoration: none;
  width: auto;
  border-radius: 8px;
  cursor: pointer;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  transition: all 0.8s ease-in;
}
.button:hover{
    box-shadow: 0 4px 6px -1px  rgb(139, 171, 162);
    transition: all 0.8s ease-out ;

}

</style>
