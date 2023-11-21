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

3. **JavaScript:**

   ```javascript
  // Function to toggle modal visibility
  const fade = (element, open) => {
    element.style.display = "flex";

    element.offsetHeight;

    const removeStyle = () => element.removeAttribute('style');

    element.addEventListener('transitionend', removeStyle);

    element.classList.toggle('open', open);
  };

  // Handle click event on document and modal triggers
  const handleClick = (event) => {
    const trigger = event.target.closest('.modal-trigger');

    const targetId = trigger?.getAttribute('data-target');
    const triggeredModal = document.getElementById(targetId);

    const isOpen = triggeredModal?.classList.contains("open");

    const activeModal = document.querySelector('.modal.open');
    // Do not close on click outside if data-backdrop is set to static
    const isStaticBackdrop = activeModal?.getAttribute('data-backdrop') === 'static';
    const modalContent = activeModal?.querySelector('.modal-content');
    const isClickedOutside = !modalContent?.contains(event.target);

    // Close active modal if clicked outside its content
    if (activeModal && !isStaticBackdrop && isClickedOutside) {
      fade(activeModal, false);
    }

    if (!trigger) return;

    // Close active modal.
    if (activeModal) fade(activeModal, false);

    // Toggle triggered modal
    fade(triggeredModal, !isOpen);
  };

  // Event delegation
  document.body.addEventListener("click", handleClick);

## Customization

**Backdrop Behavior:**

Set the `data-backdrop` attribute to `'static'` if you want to prevent closing on clicking outside the modal content.

**Styling:**

Customize the modal appearance by adjusting the provided CSS styles.

Feel free to integrate, modify, and enhance this modal component according to your project's requirements.
