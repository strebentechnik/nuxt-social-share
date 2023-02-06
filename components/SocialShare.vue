<script lang="ts" setup>
const buttonText = ref("Copy URL");
const copyUrl = () => {
  navigator.clipboard.writeText(window.location.href);
  buttonText.value = "Copied";
  setTimeout(() => {
    buttonText.value = "Copy URL";
  }, 3000);
};
const shareLink = (webURL: any) => {
  const currentUrl = window.location.href;
  window.open(`${webURL}${currentUrl}`);
};
</script>
<template>
  <div
    class="relative z-10"
    aria-labelledby="modal-title"
    role="dialog"
    aria-modal="true"
  >
    <div
      class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"
    ></div>

    <div class="fixed inset-0 z-10 overflow-y-auto">
      <div
        class="flex min-h-full items-center justify-center p-4 text-center sm:items-center sm:p-0"
      >
        <div
          class="relative transform overflow-hidden rounded-lg bg-white px-4 pt-5 pb-4 text-left shadow-xl transition-all sm:my-8 w-96 sm:w-full sm:max-w-lg sm:p-6"
        >
          <div>
            <div
              class="mx-auto flex h-12 w-12 items-center justify-center rounded-full bg-blue-50"
            >
              <svg
                class="w-6 h-6 text-blue-900"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1"
                ></path>
              </svg>
            </div>
            <div class="mt-2 text-center sm:mt-5">
              <h3 class="text-xl font-normal tracking-wide text-gray-500">
                Link Sharing
              </h3>
              <div
                class="mt-2 flex flex-grow items-center justify-around text-gray-500"
              >
                <div>
                  <button
                    type="button"
                    class="inline-flex items-center rounded-full border border-transparent bg-white p-3 text-white shadow-md"
                    @click="
                      shareLink(
                        `https://www.linkedin.com/sharing/share-offsite/?url=`
                      )
                    "
                  >
                    <img
                      src="../assets/images/linkedin.png"
                      alt=""
                      class="h-6 w-6"
                    />
                  </button>
                  <h1 class="pt-3 md:text-sm text-xs">LinkedIn</h1>
                </div>
                <div>
                  <button
                    type="button"
                    class="inline-flex items-center rounded-full border border-transparent bg-white p-3 text-white shadow-md"
                    @click="shareLink(`https://twitter.com/intent/tweet?url=`)"
                  >
                    <img
                      src="../assets/images/twitter.png"
                      alt=""
                      class="h-6 w-6"
                    />
                  </button>
                  <h1 class="pt-3 md:text-sm text-xs">Twitter</h1>
                </div>
                <div>
                  <button
                    type="button"
                    class="inline-flex items-center rounded-full border border-transparent bg-white p-3 text-white shadow-md"
                    @click="
                      shareLink(
                        `https://www.facebook.com/dialog/share?app_id=87741124305&href=`
                      )
                    "
                  >
                    <img
                      src="../assets/images/facebook.png"
                      alt=""
                      class="h-6 w-6"
                    />
                  </button>
                  <h1 class="pt-3 md:text-sm text-xs">Facebook</h1>
                </div>
                <div>
                  <button
                    type="button"
                    class="inline-flex items-center rounded-full border border-transparent bg-white p-3 text-white shadow-md"
                    @click="shareLink(`https://api.whatsapp.com/send/?text=`)"
                  >
                    <img
                      src="../assets/images/whatsapp.png"
                      alt=""
                      class="h-6 w-6"
                    />
                  </button>
                  <h1 class="pt-3 md:text-sm text-xs">Whatsapp</h1>
                </div>
                <div>
                  <button
                    type="button"
                    class="inline-flex items-center rounded-full border border-transparent bg-white p-3 text-white shadow-md"
                    @click="shareLink(`mailto:?subject=job&body=`)"
                  >
                    <img
                      src="../assets/images/mail.png"
                      alt=""
                      class="h-6 w-6"
                    />
                  </button>
                  <h1 class="pt-3 md:text-sm text-xs">Mail</h1>
                </div>
              </div>
            </div>
          </div>
          <div
            class="mt-5 sm:grid sm:grid-flow-row-dense sm:grid-cols-2 sm:gap-3"
          >
            <button
              type="button"
              class="inline-flex w-full justify-center rounded-md border border-transparent bg-blue-900 px-4 py-2 text-lg font-normal text-white shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:col-start-2 sm:text-sm"
              @click="copyUrl"
            >
              {{ buttonText }}
            </button>
            <button
              type="button"
              class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-400 bg-white px-4 py-2 text-base font-normal text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:col-start-1 sm:mt-0 sm:text-sm"
            >
              Cancel
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
