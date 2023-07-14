<script>

const formValues = {
      name: "",
      profileSummary: "",
      country: "",
      jobLocation: [], //for selecting multiple values
      remoteWork: false,
      skillSet: [],
      yearsofExperience:"",
    };
  
  
     function submitForm(){
      console.log(formValues)
     }
</script>


<main>
<!-- form handling -->
<form class="text-center border-2 border-blue-400 mt-5 mr-5 ml-5" on:submit|preventDefault={submitForm}>
    <pre>
      {JSON.stringify(formValues, null, 2)}
    </pre>
  
    <div class="my-5">
      <label for="name" class="block">Age</label>
      <input class="border border-gray-700 mt-1 p-3 w-1/4" type="number" id="name" placeholder="label is here..." bind:value={formValues.name} />
    </div>
  
    <div class="my-5">
      <label for="profile" class="block">Profile Summary</label>
      <textarea class="border border-gray-700 mt-1 p-3 w-1/2" id="profile" bind:value={formValues.profileSummary}></textarea>
    </div>
  
    <div class="my-5">
      <label for="country" class="block">Country</label>
      <select class="border border-gray-700 mt-1 p-3 w-1/4" id="country" bind:value={formValues.country}>
        <option value="">select a country</option>
        <option value="india">India</option>
        <option value="china">China</option>
        <option value="korea">Korea</option>
      </select>
    </div>
  
    <div class="my-5">
      <label for="joblocation" class="block">Location</label>
      <select class="border border-gray-700 mt-1 p-3 w-1/2" id="joblocation" bind:value={formValues.jobLocation} multiple>
        <option value="">select a country</option>
        <option value="india">India</option>
        <option value="china">China</option>
        <option value="korea">Korea</option>
      </select>
    </div>
  
    <div class="my-5">
      <input type="checkbox" id="remotework" bind:checked={formValues.remoteWork} />
      <label for="remotework" class="inline">Site work?</label>
    </div>
  
    <div class="my-5">
      <label class="block">Skill set:</label>
      <input type="checkbox" id="html" value="html" bind:group={formValues.skillSet} />
      <label for="html" class="inline">HTML5</label>
      <input type="checkbox" id="css" value="css" bind:group={formValues.skillSet} />
      <label for="css" class="inline">CSS</label>
      <input type="checkbox" id="js" value="js" bind:group={formValues.skillSet} />
      <label for="js" class="inline">JavaScript</label>
    </div>
  
    <div class="my-5">
      <label class="block">Years of Experience:</label>
      <input type="radio" id="0-2" value="0-2" bind:group={formValues.yearsofExperience} />
      <label for="0-2" class="inline">0-2</label>
      <input type="radio" id="more than 2" value="more than 2" bind:group={formValues.yearsofExperience} />
      <label for="more than 2" class="inline">More than 2</label>
    </div>
  
    <div class="my-5">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Submit</button>
    </div>
  </form>
  
</main>

<style>

</style>