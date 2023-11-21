# Modal Component

A simple modal component for creating modals with flexible and customizable features.

## Features

- Smooth modal transitions
- Customizable backdrop behavior
- Easily trigger multiple modals

## Usage

1. **HTML Structure:**

   ```html
   <button class="modal-trigger" data-target="modal1">Open Modal</button>

   <div id="modal1" class="modal" data-backdrop="static">
     <div class="modal-content">
       <!-- Your modal content goes here -->
       <p>This is a simple modal!</p>
       <button class="modal-trigger" data-target="modal1">Close Modal</button>
       <button class="modal-trigger" data-target="modal2">2nd Modal</button>
     </div>
   </div>

   <div id="modal2" class="modal">
     <div class="modal-content">
       <!-- Your modal content goes here -->
       <p>This is a simple modal!</p>
       <button class="modal-trigger" data-target="modal2">Close Modal</button>
       <button class="modal-trigger" data-target="modal1">1st Modal</button>
     </div>
   </div>
   
2. **CSS Styles:**

   Include the provided CSS styles in your stylesheet for proper modal styling.

   ```css
   <style>
    body {
      margin: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    .modal {
      display: none;
      opacity: 0;
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.5);
      align-items: center;
      justify-content: center;
      transition: all .15s ease-out;
    }

    .modal-content {
      background-color: #fff;
      padding: 1rem;
      border-radius: .3rem;
      box-shadow: 0 0 .3rem rgba(0, 0, 0, 0.3);
      transform: translateY(-50px);
      transition: all .3s ease-out;
    }

    .modal.open {
      display: flex;
      opacity: 1;
    }

    .modal.open .modal-content {
      transform: translateY(0);
    }
  </style>
   
