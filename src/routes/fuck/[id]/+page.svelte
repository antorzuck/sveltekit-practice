<script>
  import { page } from "$app/stores";

let x = ''
let loader = ''

function fetching(){
  loader = 'spinner-grow'
  let req = fetch("http://127.0.0.1:8000/api/fuck")
  .then(data=>{return data.json()})
  .then(data =>{
    x =  data.msg;
    loader = ''
  
  })
}



</script>

${x}

<button class="btn btn-primary" on:click={fetching}> click meh
  <span class="{loader}" role="status" aria-hidden="true"></span>
</button>