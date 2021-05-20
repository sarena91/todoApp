<template>
  <div class="about">
    <h3>About this app...</h3>
    <br>

    <p>This is the TodoList App v1.0.0. It is part of the Vue crash course from Traversy Media on YouTube.</p>
  
    <p>The Vue CLI was used to build and render the app. JSONplaceholder also serves as a fake API to demonstrate its functionality.</p>
    <br>

    <p><em>How it works:</em></p>
    <p>On page load, the application is populated with random todos from JSONplaceholder using a GET request.<br>
    New todo items can be added using the text input field and submit button. This sends a POST request to JSONplaceholder.<br>
    The delete button on the right of each line item sends a DELETE request and removes the individual item from the list by filtering it out.<br>
    The checkbox on the left of each item toggles its completed status.<br>
    On reload, the app returns to its initial state.</p>
  </div>
</template>

<style scoped>
  .about {
    margin: 50px auto;
    line-height: 1.5;
    width: 90%;
  }

  .about h3 {
    text-align: center;
  }
</style>
