<script>
  import StarRating from "./StarRating.svelte";
  const listOfFeedbackQuestions = [
    "How would you rate the quality of the food at our restaurant?",
    "Do you feel the services were welcoming and friendly?",
    "Did you feel convenient to place an online order through our new POS app?",
    "How was your overall experience at the restaurant?",
  ];
</script>

<div class="alert alert-success">
  Thank you for placing the order, please patiently wait!
</div>

{#each listOfFeedbackQuestions as question}
  <div>
    <h3>{question}</h3>
    <br />
    <div class="center-div">
      <StarRating />
    </div>
  </div>
{/each}

<style>
  .center-div {
    display: flex;
    justify-content: center;
  }
  h3 {
    text-align: center;
  }
</style>
