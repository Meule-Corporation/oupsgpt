<script>
import OupsGPTMessage from '@/components/OupsGPTMessage.vue'
import UserMessage from '@/components/UserMessage.vue'
import sound from '../assets/fart.mp3'

export default {
  components: {
    OupsGPTMessage,
    UserMessage
  },
  data() {
    return {
      chats: [],
      chatText: ''
    }
  },
  methods: {
    addChat() {
      this.chats.push( '' + this.chatText)
      this.chatText = ''
      const audio = new Audio(sound);
      audio.play();
    }
  }
}
</script>

<template>
  <div class="relative z-0 flex h-full w-full overflow-hidden snipcss-GoQyq">
    <div class="dark flex-shrink-0 overflow-x-hidden bg-black style-SQXxS" id="style-SQXxS">
      <div class="h-full w-[260px]">
        <div class="flex h-full min-h-0 flex-col">
          <div class="flex h-full min-h-0 flex-col transition-opacity opacity-100">
            <div class="scrollbar-trigger relative h-full w-full flex-1 items-start border-white/20">
              <h2 id="style-JO2Mb" class="style-JO2Mb">
                Chat history
              </h2>
              <nav class="flex h-full w-full flex-col px-3 pb-3.5" aria-label="Chat history">
                <div class="absolute left-0 top-0 z-20 overflow-hidden transition-all duration-500 invisible max-h-0">
                  <div class="px-3 py-3.5">
                    <div class="pb-0.5 last:pb-0" tabindex="0" data-projection-id="1">
                      <a class="group flex h-10 items-center gap-2 rounded-lg px-2 font-medium hover:bg-token-surface-primary"
                         href="/">
                        <div class="h-7 w-7 flex-shrink-0">
                          <div class="gizmo-shadow-stroke relative flex h-full items-center justify-center rounded-full bg-white text-black">
                            <img width="41" height="41"
                                src="@/assets/logo.svg"
                                 class="icon-sm" role="img" >
                          </div>
                        </div>
                        <div class="grow overflow-hidden text-ellipsis whitespace-nowrap text-sm text-token-text-primary">
                          Clear chat
                        </div>
                        <div class="flex gap-3">
                        <span class="flex items-center" data-state="closed">
                          <button class="text-token-text-primary">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                                 xmlns="http://www.w3.org/2000/svg" class="icon-md">
                              <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M4.5 2.5C5.05228 2.5 5.5 2.94772 5.5 3.5V5.07196C7.19872 3.47759 9.48483 2.5 12 2.5C17.2467 2.5 21.5 6.75329 21.5 12C21.5 17.2467 17.2467 21.5 12 21.5C7.1307 21.5 3.11828 17.8375 2.565 13.1164C2.50071 12.5679 2.89327 12.0711 3.4418 12.0068C3.99033 11.9425 4.48712 12.3351 4.5514 12.8836C4.98798 16.6089 8.15708 19.5 12 19.5C16.1421 19.5 19.5 16.1421 19.5 12C19.5 7.85786 16.1421 4.5 12 4.5C9.7796 4.5 7.7836 5.46469 6.40954 7H9C9.55228 7 10 7.44772 10 8C10 8.55228 9.55228 9 9 9H4.5C3.96064 9 3.52101 8.57299 3.50073 8.03859C3.49983 8.01771 3.49958 7.99677 3.5 7.9758V3.5C3.5 2.94772 3.94771 2.5 4.5 2.5Z"
                                    fill="currentColor">
                              </path>
                            </svg>
                          </button>
                        </span>
                        </div>
                      </a>
                    </div>
                  </div>
                </div>
                <div class="flex-col flex-1 transition-opacity duration-500 -mr-2 pr-2 overflow-y-auto">
                  <div class="sticky left-0 right-0 top-0 z-20 bg-black pt-3.5">
                    <div class="pb-0.5 last:pb-0" tabindex="0">
                      <a class="group flex h-10 items-center gap-2 rounded-lg px-2 font-medium hover:bg-token-surface-primary"
                         href="/">
                        <div class="h-7 w-7 flex-shrink-0">
                          <div class="gizmo-shadow-stroke relative flex h-full items-center justify-center rounded-full bg-white text-black">
                            <img width="41" height="41"
                                  src="@/assets/logo.svg"
                                 class="icon-sm" role="img" >
                          </div>
                        </div>
                        <div class="grow overflow-hidden text-ellipsis whitespace-nowrap text-sm text-token-text-primary">
                          Nouveau chat
                        </div>
                        <div class="flex gap-3">
                        <span class="flex items-center" data-state="closed">
                          <button class="text-token-text-primary">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                                 xmlns="http://www.w3.org/2000/svg" class="icon-md">
                              <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M16.7929 2.79289C18.0118 1.57394 19.9882 1.57394 21.2071 2.79289C22.4261 4.01184 22.4261 5.98815 21.2071 7.20711L12.7071 15.7071C12.5196 15.8946 12.2652 16 12 16H9C8.44772 16 8 15.5523 8 15V12C8 11.7348 8.10536 11.4804 8.29289 11.2929L16.7929 2.79289ZM19.7929 4.20711C19.355 3.7692 18.645 3.7692 18.2071 4.2071L10 12.4142V14H11.5858L19.7929 5.79289C20.2308 5.35499 20.2308 4.64501 19.7929 4.20711ZM6 5C5.44772 5 5 5.44771 5 6V18C5 18.5523 5.44772 19 6 19H18C18.5523 19 19 18.5523 19 18V14C19 13.4477 19.4477 13 20 13C20.5523 13 21 13.4477 21 14V18C21 19.6569 19.6569 21 18 21H6C4.34315 21 3 19.6569 3 18V6C3 4.34314 4.34315 3 6 3H10C10.5523 3 11 3.44771 11 4C11 4.55228 10.5523 5 10 5H6Z"
                                    fill="currentColor">
                              </path>
                            </svg>
                          </button>
                        </span>
                        </div>
                      </a>
                    </div>
                  </div>
                  <div class="flex flex-col gap-2 pb-2 dark:text-gray-100 text-gray-800 text-sm">
                    <div>
                    <span>
                      <div class="relative mt-5 style-5gzbx" data-projection-id="6" id="style-5gzbx">
                        <div data-projection-id="41" id="style-WBji4" class="style-WBji4">
                          <h3 class="h-9 pb-2 pt-3 px-2 text-xs font-medium text-ellipsis overflow-hidden break-all bg-white dark:bg-black text-gizmo-gray-600">
                            Aujourd'hui
                          </h3>
                        </div>
                        <ol>
                          <li class="relative z-[15] style-LUQA7" data-projection-id="42" id="style-LUQA7">
                            <div class="group relative active:opacity-90">
                              <a href="/c/06c07073-0089-42e3-8e8b-c7a70ba9a717"
                                 class="flex items-center gap-2 rounded-lg p-2 bg-token-surface-primary">
                                <div class="relative grow overflow-hidden whitespace-nowrap">
                                  Nouveau chat
                                  <div class="absolute bottom-0 right-0 top-0 w-8 bg-gradient-to-l to-transparent from-token-surface-primary">
                                  </div>
                                </div>
                              </a>
                              <div class="absolute bottom-0 right-0 top-0 flex items-center gap-1 rounded-lg bg-gradient-to-l from-token-surface-primary from-60% to-transparent pl-10 pr-1">
                                <button class="flex items-center justify-center text-token-text-primary transition hover:text-token-text-secondary radix-state-open:text-token-text-secondary"
                                        type="button" id="radix-:r23:" aria-haspopup="menu" aria-expanded="false"
                                        data-state="closed">
                                  <svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                                       xmlns="http://www.w3.org/2000/svg" class="icon-md">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                          d="M3 12C3 10.8954 3.89543 10 5 10C6.10457 10 7 10.8954 7 12C7 13.1046 6.10457 14 5 14C3.89543 14 3 13.1046 3 12ZM10 12C10 10.8954 10.8954 10 12 10C13.1046 10 14 10.8954 14 12C14 13.1046 13.1046 14 12 14C10.8954 14 10 13.1046 10 12ZM17 12C17 10.8954 17.8954 10 19 10C20.1046 10 21 10.8954 21 12C21 13.1046 20.1046 14 19 14C17.8954 14 17 13.1046 17 12Z"
                                          fill="currentColor">
                                    </path>
                                  </svg>
                                </button>
                              </div>
                            </div>
                          </li>
                        </ol>
                      </div>
                    </span>
                    </div>
                  </div>
                </div>
                <div class="flex flex-col pt-2 empty:hidden dark:border-white/20">
                  <a class="flex min-h-[44px] py-1 items-center gap-3 dark:text-white cursor-pointer text-sm dark:hover:bg-token-surface-primary hover:bg-token-surface-primary rounded-lg px-2">
                  <span class="flex w-full flex-row flex-wrap-reverse justify-between">
                    <div class="flex items-center gap-2">
                      <span class="flex h-7 w-7 items-center justify-center rounded-full border border-token-border-light bg-black">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"
                             class="icon-sm shrink-0">
                          <path d="M8.78158 8.60266L9.8188 5.49098C10.037 4.83634 10.963 4.83634 11.1812 5.49098L12.2184 8.60266C12.7187 10.1035 13.8965 11.2813 15.3973 11.7816L18.509 12.8188C19.1637 13.037 19.1637 13.963 18.509 14.1812L15.3973 15.2184C13.8965 15.7187 12.7187 16.8965 12.2184 18.3973L11.1812 21.509C10.963 22.1637 10.037 22.1637 9.8188 21.509L8.78158 18.3973C8.28128 16.8965 7.10354 15.7187 5.60266 15.2184L2.49098 14.1812C1.83634 13.963 1.83634 13.037 2.49098 12.8188L5.60266 11.7816C7.10354 11.2813 8.28128 10.1035 8.78158 8.60266Z"
                                fill="currentColor">
                          </path>
                          <path d="M17.1913 3.69537L17.6794 2.23105C17.7821 1.92298 18.2179 1.92298 18.3206 2.23105L18.8087 3.69537C19.0441 4.40167 19.5983 4.9559 20.3046 5.19133L21.769 5.67944C22.077 5.78213 22.077 6.21787 21.769 6.32056L20.3046 6.80867C19.5983 7.0441 19.0441 7.59833 18.8087 8.30463L18.3206 9.76895C18.2179 10.077 17.7821 10.077 17.6794 9.76895L17.1913 8.30463C16.9559 7.59833 16.4017 7.0441 15.6954 6.80867L14.231 6.32056C13.923 6.21787 13.923 5.78213 14.231 5.67944L15.6954 5.19133C16.4017 4.9559 16.9559 4.40167 17.1913 3.69537Z"
                                fill="currentColor">
                          </path>
                        </svg>
                      </span>
                      <div class="flex flex-col">
                        <span class="font-semibold">
                          Upgrade plan
                        </span>
                        <span class="text-xs text-token-text-secondary line-clamp-1">
                          Get Oups-GRoté, OupsGPaQuePété
                        </span>
                      </div>
                    </div>
                  </span>
                  </a>

                </div>
              </nav>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="relative flex h-full max-w-full flex-1 flex-col overflow-hidden">
      <main class="relative h-full w-full flex-1 overflow-auto transition-width">
        <div role="presentation" class="flex h-full flex-col">
          <div class="flex-1 overflow-hidden">
            <div class="react-scroll-to-bottom--css-daetg-79elbk h-full">
              <div class="react-scroll-to-bottom--css-daetg-1n7m0yu">
                <div id="yolo" class="flex flex-col pb-9 text-sm">
                  <div class="sticky top-0 mb-1.5 flex items-center justify-between z-10 h-14 bg-white p-2 font-semibold dark:bg-gray-800">
                    <div class="absolute left-1/2 -translate-x-1/2">
                    </div>
                    <div class="flex items-center gap-2">
                      <div class="group flex cursor-pointer items-center gap-1 rounded-xl py-2 px-3 text-lg font-medium hover:bg-gray-50 radix-state-open:bg-gray-50 dark:hover:bg-black/10 dark:radix-state-open:bg-black/20"
                           type="button" id="radix-:r1v:" aria-haspopup="menu" aria-expanded="false"
                           data-state="closed">
                        <div style="color: rgb(236, 236, 241)">
                          OupsGPT
                          <span class="text-token-text-secondary">
                          5.0
                        </span>
                        </div>
                      </div>
                    </div>
                  </div>

                  <template v-for="(chat, i) in chats" :key="i">

                    <UserMessage :text="chat"></UserMessage>
                    <OupsGPTMessage/>

                  </template>
                </div>
              </div>
            </div>
          </div>
          <div class="w-full pt-2 md:pt-0 dark:border-white/20 md:border-transparent md:dark:border-transparent md:w-[calc(100%-.5rem)]">
            <form class="stretch mx-2 flex flex-row gap-3 last:mb-2 md:mx-4 md:last:mb-6 lg:mx-auto lg:max-w-2xl xl:max-w-3xl">
              <div class="relative flex h-full flex-1 items-stretch md:flex-col">
                <div class="flex w-full items-center">
                  <div class="overflow-hidden [&amp;:has(textarea:focus)]:border-token-border-xheavy [&amp;:has(textarea:focus)]:shadow-[0_2px_6px_rgba(0,0,0,.05)] flex flex-col w-full dark:border-token-border-heavy flex-grow relative border border-token-border-heavy dark:text-white rounded-2xl bg-white dark:bg-gray-800 shadow-[0_0_0_2px_rgba(255,255,255,0.95)] dark:shadow-[0_0_0_2px_rgba(52,53,65,0.95)]">
                  <textarea id="prompt-textarea" tabindex="0" data-id="request-NEW:0-0" rows="1" style="color: rgb(236, 236, 241)"
                            placeholder="Une question pour OupsGPT ?"
                            v-model="chatText"
                            @keyup.enter="addChat"
                            class="m-0 w-full resize-none border-0 bg-transparent py-[10px] pr-10 focus:ring-0 focus-visible:ring-0 dark:bg-transparent md:py-3.5 md:pr-12 placeholder-black/50 dark:placeholder-white/50 pl-3 style-BeAoc">
                  </textarea>
                    <button @click.prevent="addChat"
                            class="absolute md:bottom-3 md:right-3 dark:hover:bg-gray-900 dark:disabled:hover:bg-transparent right-2 dark:disabled:bg-white disabled:bg-black disabled:opacity-10 disabled:text-gray-400 enabled:bg-black text-white p-0.5 border border-black rounded-lg dark:border-white dark:bg-white bottom-1.5 transition-colors"
                            data-testid="send-button">
                    <span class="" data-state="closed">
                      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" class="text-white dark:text-black">
                        <path d="M7 11L12 6L17 11M12 18V7" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                              stroke-linejoin="round">
                        </path>
                      </svg>
                    </span>
                    </button>
                  </div>
                </div>
              </div>
            </form>
            <div class="relative px-2 py-2 text-center text-xs text-gray-600 dark:text-gray-300 md:px-[60px]">
            <span>
              OupsGPT ne peut pas sentir mauvais, pensez a vérifier votre odeur.
            </span>
            </div>
          </div>
        </div>
        <div class="group fixed bottom-3 right-3 z-10 hidden gap-1 lg:flex">
          <div class="group relative" data-headlessui-state="">
            <button class="flex items-center justify-center rounded-full border border-gray-200 bg-gray-50 text-gray-600 dark:border-white/10 dark:bg-white/10 dark:text-gray-200"
                    id="headlessui-menu-button-:r7:" type="button" aria-haspopup="true" aria-expanded="false"
                    data-headlessui-state="">
              <a href="mailto:contact@oupsgpt.fr">
                <div class="flex h-6 w-6 items-center justify-center text-xs" >
                  ?
                </div>
              </a>
            </button>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
