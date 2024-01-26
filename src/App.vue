<template>

  <div>
    <div id="flex-div" class="flex flex-wrap pr-[7px]">

    </div>
  </div>

  <div class="buttons">
    <button @click="clearAllNotes()" :class="`bg-${currentColor} rounded-full h-[50px] w-[50px] fixed bottom-[25px] right-[120px] drop-shadow-2xl`"><img src="./assets/reset.svg" class="ml-[6px]" alt="reset"></button>
    <button @click="createNote()" :class="`bg-${currentColor} rounded-full h-[85px] w-[85px] fixed bottom-[25px] right-[25px] drop-shadow-2xl`"><img src="./assets/add-note.svg" class="ml-[14px]" alt="add"></button>
    <button @click="showColorSelection()" :class="`bg-${currentColor} rounded-full h-[50px] w-[50px] fixed bottom-[120px] right-[25px] drop-shadow-2xl`"><img src="./assets/horiz-dots.svg" class="ml-[8px]" alt="color"></button>
  
    <div class="fixed w-[200px] h-[60px] fixed bottom-[170px] right-[25px] drop-shadow-2xl">
      <div class="flex" :class="{ hidden: colorSelectionBar }">
        <button @click="changeColorToYellow()" class="w-[50px] h-[60px] bg-yellow-200 rounded-l-lg"></button>
        <button @click="changeColorToGreen()" class="w-[50px] h-[60px] bg-green-400"></button>
        <button @click="changeColorToRed()" class="w-[50px] h-[60px] bg-red-400"></button>
        <button @click="changeColorToBlue()" class="w-[50px] h-[60px] bg-blue-400 rounded-r-lg"></button>
      </div>
    </div>
  </div>

</template>

<script>

  export default {

    data() {
      return {
        colorSelectionBar: true,
        //clickCount: 1,
        currentColor: 'blue-400',
        backgroundColorBlue: 'blue-400',
        backgroundColorRed: 'red-400',
        backgroundColorGreen: 'green-400',
        backgroundColorYellow: 'yellow-200',
      }
    },
    
    methods: {
      createNote() {
        let flexDiv = document.getElementById('flex-div')

        let newNote = document.createElement('div')
        newNote.className = 'w-full pl-[7px] md:w-1/2 lg:w-1/4 xl:w-1/4 pt-[6px]'
        flexDiv.appendChild(newNote)

        let newNoteBluePart = document.createElement('div')
        newNoteBluePart.className = `blue-top-cl bg-${this.currentColor} w-full h-[50px] flex justify-end rounded-t-[12px]`
        newNote.appendChild(newNoteBluePart)

        let newNoteTextArea = document.createElement('textarea')
        newNoteTextArea.className = 'note-cl bg-stone-500 w-full min-h-[200px] h-fit rounded-b-[12px] drop-shadow-2xl p-[6px] text-slate-100 overflow-auto focus:outline-none focus:border-[1px] focus:ring-slate-300'
        newNote.appendChild(newNoteTextArea)

        let newNoteDeleteButton = document.createElement('button')
        newNoteDeleteButton.textContent = '+'
        newNoteDeleteButton.className = 'h-[40px] w-[40px] mt-[5px] mr-[7px] cursor-pointer text-white text-4xl rotate-45'
        newNoteBluePart.appendChild(newNoteDeleteButton)

        //let makeBoldSelectionButton = document.createElement('button')
        //makeBoldSelectionButton.className = `bg-${this.currentColor} rounded-full h-[50px] w-[50px] fixed bottom-[220px] right-[25px] drop-shadow-2xl`
        //newNoteBluePart.appendChild(makeBoldSelectionButton)

        newNoteDeleteButton.addEventListener('click', function() {
          flexDiv.removeChild(newNote)
        })

        //makeBoldSelectionButton.addEventListener('click', function(){
        //  this.toggleBold()
        //})
      },

      showColorSelection() {
        this.colorSelectionBar = !this.colorSelectionBar
      },

      changeColorToBlue() {
        this.currentColor = this.backgroundColorBlue
      },

      changeColorToGreen() {
        this.currentColor = this.backgroundColorGreen
      },

      changeColorToYellow() {
        this.currentColor = this.backgroundColorYellow
      },

      changeColorToRed() {
        this.currentColor = this.backgroundColorRed
      },

      //toggleBold() {
      //const selection = window.getSelection();
      //const selectedText = selection.toString();

      //if (selectedText !== '') {
      //  const range = selection.getRangeAt(0);
      //  const span = document.createElement('span');
      //  span.style.fontWeight = range.commonAncestorContainer.parentNode.style.fontWeight === 'bold' ? 'normal' : 'bold';
      //  range.surroundContents(span);
      //  }
      //},

    //  changeColorOfEverything() {
     //   switch(true) {
     //     case : 
     //   }
     // }

      //changeColorOfEverything('yellow') {
        //this.showColorSelection()

      //}
      //showColorSelection() {
      //  this.colorSelectionBar = false
      //  this.clickCount++

      //  if( (this.clickCount % 2) == 1) {
      //    this.hideColorSelectionBar()
      //  }
      //},

      //hideColorSelectionBar() {
      //  this.colorSelectionBar = true
      //}

      
    },
  }

</script>

<style>


</style>