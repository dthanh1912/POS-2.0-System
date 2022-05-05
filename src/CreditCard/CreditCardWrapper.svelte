<script>
  import CreditCardPayment from "./CreditCardPayment.svelte";
  import FeedBack from "../StarRating/Feedback.svelte";
  export let total_price;
  let alreadyPay = false;

  function handlePay(event) {
    alreadyPay = event.detail.option;
  }
</script>

{#if alreadyPay}
  <FeedBack />
{:else}
  <CreditCardPayment bind:total_price on:pay={handlePay} />
{/if}
