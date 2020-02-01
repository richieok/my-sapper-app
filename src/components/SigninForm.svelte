<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let url = "";
  export let errorList = [];
  let formData = {
    username: "",
    password: ""
  };
  function handleSubmit(e) {
    dispatch('formSubmit', {
      url: url,
      formData: formData
    })
    // console.log(`email/username: ${formData.username}\npassword: ${formData.password}`)
    // postData("http://127.0.0.1:5515/auth/signin", formData);
  }
//   async function postData(url, data) {
//     let resp = await fetch(url, {
//       method: "POST",
//       headers: { "Content-Type": "application/json;charset=utf-8" },
//       body: JSON.stringify(data)
//     });
//     if (resp.ok) {
//       const jsonData = await resp.json();
//       console.log(jsonData);
//     } else {
//       console.log(resp.status);
//       const jsonData = await resp.json();
//       console.log(jsonData);
//     }
//   }
</script>

<style>
:root {
    --dark-transparent: rgba(0, 0, 0, 0.2);
  }

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
    background-color: var(--dark-transparent);
    padding: 20px;
  }

  form label {
    width: 130px;
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
      <label for="username">Username:</label>
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
    <div>
      <button type="submit">Submit</button>
    </div>
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
