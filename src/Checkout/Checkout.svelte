<script>
  import {
    Button,
    Modal,
    ModalBody,
    ModalFooter,
    ModalHeader,
  } from "sveltestrap";
  let open = false;
  let orderID = "";
  const toggle = () => {
    open = !open;
    orderID = orderCodeGenerate();
  };
  import CheckoutItem from "./CheckoutItem.svelte";
  import { cart } from "../Stores/stores.js";
  import CreditCardWrapper from "../CreditCard/CreditCardWrapper.svelte";
  import Feedback from "../StarRating/Feedback.svelte";

  let checkedOut = false;
  let paymentMethod = "";
  let cartItems = [];
  let price_sum = 0;
  let cart_sum = 0;
  let pass_price_sum = 0;

  cart.subscribe((items) => {
    cartItems = Object.values(items); 
    cart_sum = 0;
    price_sum = 0;
    cartItems.forEach((item) => {
      cart_sum += item.count;
      price_sum += item.price*item.count;
    });
  });

  const checkout = (payMethod) => () => {
    // alert("Hello");
    paymentMethod = payMethod;
    checkedOut = true;
    pass_price_sum = price_sum;
    cart.update((n) => {
      return {};
    });
  };
  function orderCodeGenerate() {
    var text = "";
    var characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    var numbers = "0123456789";

    for (var i = 0; i < 4; i++) {
      text += characters.charAt(Math.floor(Math.random() * characters.length));
    }
    for (var i = 0; i < 5; i++) {
      text += numbers.charAt(Math.floor(Math.random() * numbers.length));
    }
    return text;
  }
</script>

<div class="container">
  <div class="row">
    <div class="col-sm">
      {#if cartItems.length === 0}
        {#if checkedOut}
          <h1>My Order: {orderID}</h1>
          {#if paymentMethod === "credit_card"}
            <!-- <CreditCardPayment total_price={10000} /> -->
            <CreditCardWrapper bind:total_price={pass_price_sum}/>
          {:else if paymentMethod === "cash"}
            <Feedback />
          {/if}
        {:else}
          <h1>My Cart</h1>
          <div class="alert alert-warning">
            <strong>Your cart is currently empty! </strong> Please add some food~
          </div>
      {/if}
      {:else}
        <h1>My Cart</h1>
        <div class="row">
          {#each cartItems as item (item.name)}
            <div class="col-md-4">
              <CheckoutItem {item} />
            </div>
          {/each}
        </div>
        <br/>

        <Button class="btn btn-success btn-lg btn-block" on:click={toggle}>
          Checkout : ${price_sum}
        </Button>

        <Modal isOpen={open} {toggle} backdrop="static">
          <ModalHeader {toggle}>Order success! Thank you~</ModalHeader>
          <ModalBody>
            <div class="image-container">
              <img
                src="img/burger-dribble.gif"
                width="146"
                height="168"
                alt="The restaurant is preparing your dish"
              />
            </div>
            <div class="text-center">
              <h6>The restaurant is preparing your meal</h6>
              <h3>Your order code:</h3>
              <h2><strong>{orderID}</strong></h2>
            </div>
          </ModalBody>
          <ModalFooter>
            <Button color="primary" on:click={checkout("credit_card")} block
              >Credit card</Button
            >
            <Button color="danger" on:click={checkout("cash")} block
              >Cash</Button
            >
          </ModalFooter>
        </Modal>
      {/if}
    </div>
  </div>
</div>

<style>
  .image-container {
    display: flex;
    justify-content: center;
  }
  .text-center {
    text-align: center;
  }
</style>
