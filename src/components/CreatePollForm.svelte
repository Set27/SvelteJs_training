<script>
    import Button from "../share/Button.svelte";

  let fields = {
    question: "",
    answerA: "",
    answerB: "",
  };

  const submitHandler = () => {
    console.log(fields);
  };
</script>

<div class="form-container">
  <form on:submit|preventDefault={submitHandler}>
    <div class="form-field">
      <label for="question">Poll question:</label>
      <input type="text" id="question" bind:value={fields.question} />
    </div>
    <div class="form-field">
      <label for="answer-a">Poll answer:</label>
      <input type="text" id="answer-a" bind:value={fields.answerA} />
    </div>
    <div class="form-field">
      <label for="answer-b">Poll answer:</label>
      <input type="text" id="answer-b" bind:value={fields.answerB} />
    </div>
    <Button type="primary">
      Add Poll
    </Button>
    <!-- <button>Add Poll</button> -->
  </form>
</div>

<style>
  .form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
    width: 60%;
    padding: 20px;
  }

  .form-field {
    margin-bottom: 15px;
  }

  label {
    display: block;
    font-weight: bold;
    margin-bottom: 5px;
  }

  input {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    transition: border-color 0.3s ease-in-out;
  }

  input:focus {
    border-color: #007bff;
  }

</style>
