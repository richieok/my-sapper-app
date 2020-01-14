<script>
  import {createEventDispatcher} from "svelte";
  import RegisterForm from "../components/RegisterForm.svelte";
  const dispatch = createEventDispatcher();
  let url = 'http://localhost:5515/auth/signup';
  let errorList = [];

  function handleSubmit(event){
    errorList = [];
    const data = event.detail.formData;
    if (data.password !== data.confirm_password){
      errorList.push({id: '1', msg: "Password's must match"});
      errorList = errorList;
    } else {
      errorList = [];
    }
    console.log(data);
    console.log(event.detail.url);
    console.log(errorList);
  }
</script>
<RegisterForm {url} on:formSubmit={handleSubmit} {errorList}/>