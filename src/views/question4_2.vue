<template>
  <button class="btn-checkout-border">
    <div class="btn-checkout">
      <div class="text-checkout">
        <i class="fa fa-star" aria-hidden="true"/>
        CHECKOUT
        <i class="fa fa-star" aria-hidden="true"/>
      </div>
    </div>
  </button>
</template>

<script>
  export default {
    name: "question4_2"
  }
</script>

<style scoped>
  .btn-checkout-border {
    padding: 5px;
    border: 1px solid #666666;
    border-radius: 20px;
    outline: 0;
    background: rgba(226,226,226,1);
  }
  .btn-checkout {
    padding: 10px 15px;
    border-radius: 16px;
    border-color: transparent;
    background: linear-gradient(180deg, rgba(226,226,226,1) 0%, rgba(191,191,191,1) 50%, rgba(173,173,173,1) 100%);
    box-shadow: 0 0px 5px rgba(50,50,93,.5), 0px 0px 5px rgba(0,0,0,.4);
  }
  .btn-checkout-border:hover {
    border-color: #C3AE48;
    background: rgba(255,211,0,1);
  }
  .btn-checkout-border:hover .btn-checkout {
    background: linear-gradient(180deg, rgba(255,211,0,1) 0%, rgba(255,233,0,1) 100%, rgba(255,237,0,1) 100%);
    box-shadow: 0 0px 5px rgba(50,50,93,.5), 0px 0px 5px rgba(255,255,255,.4);
  }
  .text-checkout {
    font-weight: 900;
    color: #575461;
  }
  .text-checkout i {
    color: #868686
  }
  .btn-checkout-border:hover .btn-checkout .text-checkout i, .btn-checkout-border:hover .btn-checkout .text-checkout {
    color: #FFFFFF
  }
</style>