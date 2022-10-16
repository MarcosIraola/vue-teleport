<template>
    <div >
      <div id="open-modal" :class="{ show, 'modal-window': true }">
        <div class="modal">
          <a @click="show = false" title="Close" class="modal-close">Close</a>
          <h1>{{ title }}</h1>
          <div>
            <slot></slot>
          </div>
          <div>
            <small>{{ sub }}</small>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ["title", "sub"],
    data() {
      return {
        show: false
      };
    }

  };
  </script>
  
  <style scoped>
  .modal-window div:not(:last-of-type) {
    margin-bottom: 15px;
  }
  .modal-window {
    background-color: rgb(134, 134, 134);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 10000;
    opacity: 0;
    transition: all 0.3s;
  }

  div {
      width: 400px;
      height: 300px;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 2em;
    }

  .show {
    visibility: visible;
    opacity: 1;
    pointer-events: auto;
  }

  .modal {
    display: flex;
    flex-direction: column;
  }
  .modal-close {
    color: #aaa;
    line-height: 50px;
    font-size: 80%;
    position: absolute;
    right: 0;
    text-align: center;
    top: 0;
    width: 70px;
    text-decoration: none;
    z-index: 1000;
    cursor: pointer;
  }
  .modal-close:hover {
    color: black;
  }
  </style>