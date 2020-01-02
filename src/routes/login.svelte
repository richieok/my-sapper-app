<script>
  import {createEventDispatcher} from "svelte";
  const dispatch = createEventDispatcher();
  export let url = '';
  let formData = {
    email: '',
    password: ''
  }
  function handleSubmit(){
    dispatch('formSubmit', {
      url: url,
      formData: formData
    })
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
    width: 130px;
  }
</style>

<div>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group">
      <label for="email">Username:</label>
      <input type="text" id="email" bind:value={formData.email} class="form-control" />
    </div>
    <div class="form-group">
      <label for="password">Password:</label>
      <input type="password" id="password" bind:value={formData.password} class="form-control" />
    </div>
    <div>
      <button type="submit">Submit</button>
    </div>
  </form>
</div>
