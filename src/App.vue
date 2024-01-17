<template>

  <div>
    <div id="flex-div" class="flex flex-wrap pr-[7px]">

    </div>
  </div>

  <div class="buttons">
    <button class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[25px] right-[120px] drop-shadow-2xl"><img src="./assets/reset.svg" class="ml-[6px]" alt="reset"></button>
    <button @click="createNote()" class="bg-blue-600 rounded-full h-[85px] w-[85px] fixed bottom-[25px] right-[25px] drop-shadow-2xl"><img src="./assets/add-note.svg" class="ml-[14px]" alt="add"></button>
    <button @click="showColorSelection()" class="bg-blue-600 rounded-full h-[50px] w-[50px] fixed bottom-[120px] right-[25px] drop-shadow-2xl"><img src="./assets/horiz-dots.svg" class="ml-[8px]" alt="color"></button>
  
    <div class="fixed w-[200px] h-[60px] fixed bottom-[170px] right-[25px] drop-shadow-2xl">
      <div class="flex" :class="{ hidden: colorSelectionBar }">
        <button class="w-[50px] h-[60px] bg-yellow-300 rounded-l-lg"></button>
        <button class="w-[50px] h-[60px] bg-green-400"></button>
        <button class="w-[50px] h-[60px] bg-red-400"></button>
        <button class="w-[50px] h-[60px] bg-blue-400 rounded-r-lg"></button>
      </div>
    </div>
  </div>

</template>

<script>

  export default {

    data() {
      return {
        colorSelectionBar: true
      }
    },
    
    methods: {
      createNote() {
        let flexDiv = document.getElementById('flex-div')

        let newNote = document.createElement('div')
        newNote.className = 'w-full pl-[7px] md:w-1/2 lg:w-1/4 xl:w-1/4 pt-[6px]'
        flexDiv.appendChild(newNote)

        let newNoteBluePart = document.createElement('div')
        newNoteBluePart.className = 'blue-top-cl bg-blue-600 w-full h-[50px] flex justify-end rounded-t-[12px]'
        newNote.appendChild(newNoteBluePart)

        let newNoteTextArea = document.createElement('textarea')
        newNoteTextArea.className = 'note-cl bg-stone-600 w-full min-h-[200px] h-fit rounded-b-[12px] drop-shadow-2xl p-[6px] text-slate-100 overflow-auto'
        newNote.appendChild(newNoteTextArea)

        let newNoteDeleteButton = document.createElement('button')
        newNoteDeleteButton.textContent = '+'
        newNoteDeleteButton.className = 'h-[40px] w-[40px] mt-[5px] mr-[7px] cursor-pointer text-white text-4xl rotate-45'
        newNoteBluePart.appendChild(newNoteDeleteButton)

        newNoteDeleteButton.addEventListener('click', function() {
          flexDiv.removeChild(newNote)
        })
      },

      deleteNote() {
        
      },

      showColorSelection() {
        this.colorSelectionBar = false
      }
    }

  }

</script>

<style>

  

</style>
