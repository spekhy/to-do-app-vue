<template>

  <div id="app">
    <div id="notes">
        <div id="first-note" class="first-note-cl">
            <div id="blue-top" class="blue-top-cl bg-blue-600 w-3/12 h-[50px] flex justify-end rounded-t-[12px]"><button id="svg-delete-button" class="h-[40px] w-[40px] mt-[5px] mr-[7px] cursor-pointer"><img src="./assets/add-note.svg" class="niczatial"></button></div>
            <textarea id="note" class="note-cl bg-stone-600  w-3/12 min-h-[200px]	rounded-b-[12px] drop-shadow-2xl p-[6px]"></textarea>
        </div>
    </div>

    <div class="buttons">
        <button class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[25px] right-[120px] drop-shadow-2xl"><img src="./assets/reset.svg" class="ml-[6px]" alt="reset"></button>
        <button @click="createNote()" class="bg-blue-600 rounded-full h-[85px] w-[85px] fixed bottom-[25px] right-[25px] drop-shadow-2xl"><img src="./assets/add-note.svg" class="ml-[14px]" alt="add"></button>
        <button class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[120px] right-[25px] drop-shadow-2xl"><img src="./assets/horiz-dots.svg" class="ml-[8px]" alt="color"></button>
    </div>
  </div>

</template>

<script>

  export default {
    
    methods: {
      createNote() {
        let newNote = document.createElement('div');
        newNote.className = 'newNote';
        document.body.appendChild(newNote);

        let newNoteBluePart = document.createElement('div');
        newNoteBluePart.className = 'blue-top-cl bg-blue-600 w-3/12 h-[50px] flex justify-end rounded-t-[12px]';
        newNote.appendChild(newNoteBluePart);

        let newNoteTextArea = document.createElement('textarea');
        newNoteTextArea.className = 'note-cl bg-stone-600 w-3/12 min-h-[200px] rounded-b-[12px] drop-shadow-2xl p-[6px]';
        newNote.appendChild(newNoteTextArea);

        let newNoteDeleteButton = document.createElement('button');
        newNoteDeleteButton.className = 'h-[40px] w-[40px] mt-[5px] mr-[7px] cursor-pointer';
        newNoteBluePart.appendChild(newNoteDeleteButton);

        let newNoteDeleteButtonSvg = document.createElement('img');
        newNoteDeleteButtonSvg.src = './assets/add-note.svg';
        newNoteDeleteButtonSvg.className = 'niczatial';
        newNoteDeleteButton.appendChild(newNoteDeleteButtonSvg);

        newNoteDeleteButton.addEventListener('click', function() {
          document.body.removeChild(newNote);
        })
      },

      deleteNote() {
        
      }
    }

  }

</script>

<style>

  body {
    padding: 10px;
  }

</style>
