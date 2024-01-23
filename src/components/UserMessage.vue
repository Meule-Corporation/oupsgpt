<template>
  <div class="w-full text-token-text-primary style-r9h5A"
       data-testid="conversation-turn-3" id="style-r9h5A">
    <div class="px-4 py-2 justify-center text-base md:gap-6 m-auto">

          <div
            class="flex flex-1 text-base mx-auto gap-3 md:px-5 lg:px-1 xl:px-5 md:max-w-3xl lg:max-w-[40rem] xl:max-w-[48rem] group">
            <div class="flex-shrink-0 flex flex-col relative items-end">
              <div>
                <div class="pt-0.5">
                  <div
                    class="gizmo-shadow-stroke flex h-6 w-6 items-center justify-center overflow-hidden rounded-full">
                    <div class="relative flex">

                    </div>
                  </div>
              </div>

          </div>
        </div>
        <div class="relative flex w-full flex-col lg:w-[calc(100%-115px)]">
          <div class="font-semibold select-none">
            You
          </div>
          <div class="flex-col gap-1 md:gap-3">
            <div class="flex flex-grow flex-col max-w-full">
              <div>
                <div class="">
                  {{text}}
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
  props: {
    text: String
  }
}

</script>