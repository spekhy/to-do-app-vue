<template>

  <div id="app">
    <div id="notes">
        <div id="first-note" class="first-note-cl">
            <div id="blue-top" class="blue-top-cl"><button id="svg-delete-button" class="svg-delete-button-cl"><img src="./assets/add-note.svg" alt="add" class="svg-delete"></button></div>
            <textarea id="note" class="note-cl"></textarea>
        </div>
    </div>

    <div class="buttons">
        <button id="but-reset" class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[25px] right-[120px]"><img src="./assets/reset.svg" class="ml-[6px]" alt="reset"></button>
        <button id="but-add-note" @click="createNote()" class="bg-blue-600 rounded-full h-[85px] w-[85px] fixed bottom-[25px] right-[25px]"><img src="./assets/add-note.svg" class="ml-[14px]" alt="add"></button>
        <button id="but-color-change" class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[120px] right-[25px]"><img src="./assets/horiz-dots.svg" class="ml-[8px]" alt="color"></button>
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
