<template>
    <ul>
      <li>
        <button
          type="button"
        >
          First
        </button>
      </li>
  
      <li>
        <button
          type="button"
        >
          Previous
        </button>
      </li>
  
      <!-- Visible Buttons Start -->
  
      <!-- ... -->
  
      <!-- Visible Buttons End -->
  
      <li>
        <button
          type="button"
        >
          Next
        </button>
      </li>
  
      <li>
        <button
          type="button"
        >
          Last
        </button>
      </li>
    </ul>
  </template>
  
  <script>
  export default {
    props: {
      maxVisibleButtons: {
        type: Number,
        required: false,
        default: 3
      },    
      totalPages: {
        type: Number,
        required: true
      },
      perPage: {
        type: Number,
        required: true
      },
      currentPage: {
        type: Number,
        required: true
      }
    }
  };
  </script>