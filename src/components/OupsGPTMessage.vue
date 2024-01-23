<template>
  <div class="w-full text-token-text-primary style-r9h5A"
       data-testid="conversation-turn-3" id="style-r9h5A">
    <div class="px-4 py-2 justify-center text-base md:gap-6 m-auto">
      <div
        class="flex flex-1 text-base mx-auto gap-3 md:px-5 lg:px-1 xl:px-5 md:max-w-3xl lg:max-w-[40rem] xl:max-w-[48rem] group final-completion">
        <div class="flex-shrink-0 flex flex-col relative items-end">
          <div>
            <div class="pt-0.5">
              <div class="gizmo-shadow-stroke flex h-6 w-6 items-center justify-center overflow-hidden rounded-full">
                <div class="relative p-1 rounded-sm h-9 w-9 text-white flex items-center justify-center style-YH3dh"
                     id="style-YH3dh">
                  <img width="41" height="41" viewBox="0 0 41 41"
                       fill="none" src="@/assets/logo.svg"
                       class="icon-sm" role="img" >
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="relative flex w-full flex-col lg:w-[calc(100%-115px)] agent-turn">
          <div class="font-semibold select-none">
            OupsGPT
          </div>
          <div class="flex-col gap-1 md:gap-3">
            <div class="flex flex-grow flex-col max-w-full">
              <div
              >
                <div class="markdown prose w-full break-words dark:prose-invert dark">
                  <p>
                    {{ displayedText }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'OupsGPTMessage',
  data() {
    return {
      originalText: 'Oups, j\'ai pété.',
      words: [],
      displayedText: "",
      tempo: 100, // Tempo in milliseconds
      currentIndex: 0
    };
  },
  mounted() {
    this.splitWords();
    this.displayWords();
  },
  methods: {
    splitWords() {
      this.words = this.originalText.split(" ");
    },
    displayWords() {
      const intervalId = setInterval(() => {
        if (this.currentIndex < this.words.length) {
          this.displayedText += this.words[this.currentIndex] + " ";
          this.currentIndex++;
        } else {
          clearInterval(intervalId);
        }
      }, this.tempo);
    }
  }
};
</script>