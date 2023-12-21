<template>

  <div id="app">
    <div id="notes">
        <div id="first-note" class="first-note-cl">
            <div id="blue-top" class="blue-top-cl"><button id="svg-delete-button" class="svg-delete-button-cl"><img src="./assets/add-note.svg" alt="add" class="svg-delete"></button></div>
            <textarea id="note" class="note-cl"></textarea>
        </div>
    </div>

    <div class="buttons">
        <button id="but-reset"><img src="./assets/reset.svg" alt="reset"></button>
        <button id="but-add-note" @click="createNote()" class="bg-blue"><img src="./assets/add-note.svg" alt="add"></button>
        <button id="but-color-change"><img src="./assets/horiz-dots.svg" alt="color"></button>
    </div>
  </div>

</template>

<script>

  export default {
    
    methods: {
      createNote() {
        let div = document.createElement('div');
        div.className = 'nie';
        document.body.appendChild(div);
      }
    }

  }

</script>

<style>
</style>
