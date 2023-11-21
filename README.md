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
   Include the provided CSS styles in your      stylesheet for proper modal styling.
   
