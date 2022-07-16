<script>
    import CartsItem from '../Cart/Cart-store'
    import Button from "../UI/Button.svelte";
      
    export let id;
    export let title;
    export let price;
    export let description;
  
    function addToCart() {
      // console.log("add to cart button")
      CartsItem.update(CrtItm =>{
        return[...CrtItm, 
        {
          id: id,
          title: title,
          price: price 
        }]
      } )
    }
  </script>
  
  <style>
    .product {
      background: white;
      border-radius: 5px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      margin: 1rem 0;
    }
  
  </style>
  
  <div class="product">
    <div>
      <h1 class="text-gray-700 text-2xl font-sans">
        {title}
      </h1>
      <h2 class="text-gray-700 text-3xl font-extrabold">
        {price}
      </h2>
      <p class="text-gray-700 font-normal">{description}</p>
    </div>
    <div class="border flex">
      <Button on:click={addToCart}>Add to Cart</Button>
    </div>
  </div>
  