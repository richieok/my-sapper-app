<script>
  import {createEventDispatcher} from "svelte";
  import SigninForm from '../components/SigninForm.svelte'
  // const dispatch = createEventDispatcher();
  let url = 'http://localhost:5515/auth/signup';
  let errorList = [];
  
  function handleSubmit(e){
    const data = e.detail.formData;
    // console.log(`email/username: ${data.username}\npassword: ${data.password}`);
    postData('http://127.0.0.1:5515/auth/signin', data);
  }
  async function postData(url, data){
    errorList = [];
    let resp = await fetch(url, {
      method: 'POST',
      headers: {"Content-Type": "application/json;charset=utf-8"},
      body: JSON.stringify(data)
    });
    if(resp.ok){
      const jsonData = await resp.json();
      console.log(jsonData);
    } else {
      console.log(resp.status);
      const jsonData = await resp.json();
      console.log(jsonData);
      errorList = [{id: 1, msg: jsonData.flashMessage}]
    }
  }
</script>

<SigninForm on:formSubmit={handleSubmit} {url} {errorList}/>