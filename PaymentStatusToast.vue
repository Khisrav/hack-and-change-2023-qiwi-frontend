<template>
  <div class="toast toast-middle toast-center z-50 mx-2px sm:toast-end w-auto box-border">
          <div id="Success" class="w-auto">
            <button role="alert" @click="Close('Success')"
              class="alert alert-success text-md sm:text-lg bg-white text-green-600 shadow-md  flex">
              <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current shrink-0 h-10 sm:h-12" fill="none"
                viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <p>Your purchase has been confirmed!</p>
            </button>
          </div>
          <div id="Error" class=" w-auto">
            <button role="alert"  @click="Close('Error')"
              class="alert alert-error  text-md sm:text-lg bg-white text-red-600 shadow-md flex">
              <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current shrink-0 h-10 sm:h-12" fill="none"
                viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <p class="float-right">Error! Task failed successfully.</p>
            </button>
          </div>
        </div>
</template>
<script>
export default {
  name: 'PaymentStatusToast',
  methods: {
    Close(a) {
      const Close = document.getElementById(a)
      Close.style.display = "none"
    }
  }
}
</script>
