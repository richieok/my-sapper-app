<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let url = "";
  export let errorList = [];

  let formData = {
    firstname: "",
    lastname: "",
    username: "",
    password: "",
    confirm_password: ""
  };

  function handleSubmit(e) {
    dispatch("formSubmit", {
      url: url,
      formData: formData
    });
  }
</script>

<style>
  .form-control:active {
    border: solid 1px blue;
  }

  .form-group {
    display: flex;
    margin: 5px;
  }

  form {
    width: 80%;
    margin: auto;
    background-color: darkgrey;
    padding: 20px;
  }

  form label {
    width: 200px;
  }

  button {
    background-color: dimgray;
    border: 1px solid dimgray;
    border-radius: 4px;
  }
</style>

<div>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group">
      <label for="">First Name:</label>
      <input
        type="text"
        id="firstname"
        bind:value={formData.firstname}
        class="form-control" />
      <label for="">Last Name:</label>
      <input
        type="text"
        id="lastname"
        bind:value={formData.lastname}
        class="form-control" />
    </div>
    <div class="form-group">
      <label for="username">Email:</label>
      <input
        type="text"
        id="username"
        bind:value={formData.username}
        class="form-control" />
    </div>
    <div class="form-group">
      <label for="password">Password:</label>
      <input
        type="password"
        id="password"
        bind:value={formData.password}
        class="form-control" />
    </div>
    <div class="form-group">
      <label for="password">Confirm Password:</label>
      <input
        type="password"
        id="confirm_password"
        bind:value={formData.confirm_password}
        class="form-control" />
    </div>
    <button type="submit">Submit</button>
    <div>
      {#if errorList}
        <ul>
          {#each errorList as item}
            <li>{item.msg}</li>
          {/each}
        </ul>
      {/if}
    </div>
  </form>
</div>
