<script>
  import {
    Button,
    Modal,
    ModalBody,
    ModalFooter,
    ModalHeader,
  } from "sveltestrap";
  let open = false;
  const toggle = () => (open = !open);

  import { cart } from "../Stores/stores.js";
  export let item;
  let { name, price, img, count } = item;
  const countButtonHandler = (e) => {
    if (e.target.classList.contains("add")) {
      count++;
    } else if (count >= 1) {
      count--;
      if (count == 0) {
        alert("The item amount has reached 0! It is now removed!");
        removeItem();
        delete n[name];
        return n;
      }
    }

    cart.update((n) => ({ ...n, [name]: { ...n[name], count } }));
  };
  const removeItem = () => {
    cart.update((n) => {
      delete n[name];
      return n;
    });
  };
</script>

<div class="container">
  <div class="row">
    <img
      class="img-fluid img-thumbnail"
      src={`img/${img}`}
      alt={name}
      style="float:left;width:350px;height:250px"
    />

    <div class="item-meta-data">
      <h3 class="title">{name}</h3>
      <p class="price">Unit price: $ {price}</p>
      <p class="totalPrice">Total price: $ {price * count}</p>

      <div class="col">
        <Button 
          class="btn btn-warning"
          color="warning" 
          on:click={countButtonHandler}>-
        </Button>
        {" "}
        <Button 
          class="count"
          color="default">{count}
        </Button>
        {" "}
        <Button 
          class="btn btn-success add" 
          color="success"
          on:click={countButtonHandler}>+
        </Button>
        {" "}
        <Button class="btn btn-remove" color="danger" on:click={toggle}>
          Remove
        </Button>
        <Modal isOpen={open} {toggle} backdrop="static">
          <ModalHeader {toggle}>Warning</ModalHeader>
          <ModalBody>
            Are you sure to remove <strong>"{name}"</strong> from the cart?
          </ModalBody>
          <ModalFooter>
            <Button color="primary" on:click={removeItem}>Yes</Button>
            <Button color="secondary" on:click={toggle}>No</Button>
          </ModalFooter>
        </Modal>
      </div>
    </div>
  </div>
</div>

<style>
  .container {
    margin: 1%;
  }
</style>
