<style src="./Menu.css"></style>

<template>
  <div class="card-container">
    <div>
      <h3>
        <strong>Please choose from our delicious pizzazzzz!</strong>
      </h3>
    </div>
    <div class="table">
      <div class="row">Size</div>
      <div class="row">Price</div>
      <div class="row">Add to basket</div>
    </div>
    <div v-for="item in menuItems" :key="item.id">
      <div class="row">
        <strong>{{ item.name }}</strong>
      </div>
      <div class="table" v-for="option in item.options" :key="option.size">
        <div class="row">{{ option.size }}</div>
        <div class="row">{{ option.price }}</div>
        <div class="row">
          <button class="button" type="button">+</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      menuItems: []
    };
  },
  //this is different because it uses an arrow function.
  //   data: () => ({
  //     menuItems: []
  //   }),
  //Arrow functions are fine until we need to access a component method,
  // as we need to make use of this and such property is not bound to the
  //component using arrow functions.
  //So it's mandatory to use regular functions rather than arrow functions.
  created: function() {
    fetch("http://localhost:3000/menuItems")
      .then(response => response.json())
      .then(data => (this.menuItems = data));
  }
};
</script>
