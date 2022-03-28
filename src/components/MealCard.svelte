<!-- //============================ Script ================================= -->
<script>
  import { fade } from "svelte/transition";
  export let meal;
</script>

<!-- //============================= HTML ================================== -->
<div
  class="meal_card flex flex-col shrink grow text-center p-px  m-4 rounded-md bg-white basis-1/3 md:basis-1/4"
>
  <div class="meal_card_pic">
    <img
      class="rounded-md bg-no-repeat bg-cover w-100"
      src={meal.picture}
      alt={meal.alt}
    />
  </div>
  <div class="meal_card_title mb-2 mt-4">
    <h2 class="text-black text-4xl font-thin">{meal.title}</h2>
  </div>
  <div class="meal_card_body mb-2 p-4 max-h-fit ">
    <p class="text-left font-light leading-relaxed mt-0 mb-4 text-gray-800">
      {meal.text}
    </p>
  </div>
  <div class="flex meal_card_footer mt-1 mb-1 pl-4 pr-4 justify-start ">
    <button
      class="leading-tight rounded border p-1.5 border-zinc-700"
      type="button"
      data-bs-toggle="modal"
      data-bs-target={"#exampleModal" + meal.id}
      data-mdb-ripple="true"
      data-mdb-ripple-color="light"
    >
      Decouvrir
    </button>
  </div>
</div>

<!-- Modal -->
<div
  class="modal fade fixed top-0 left-0 hidden w-full h-full outline-none overflow-x-hidden overflow-y-auto"
  id={"exampleModal" + meal.id}
  tabindex="-1"
  aria-labelledby="exampleModalLabel"
  aria-hidden="true"
  transition:fade
>
  <div
    class="modal-dialog relative flex justify-center items-center h-screen w-auto pointer-events-none"
  >
    <div
      class="modal-content border-none shadow-lg relative flex flex-col w-full pointer-events-auto bg-white bg-clip-padding rounded-md outline-none text-current"
    >
      <div
        class="modal-header flex flex-shrink-0 items-center justify-between p-4 border-b border-gray-200 rounded-t-md"
      >
        <h5
          class="text-xl font-medium leading-normal text-gray-800"
          id="exampleModalLabel"
        >
          {meal.title}
        </h5>
        <button
          type="button"
          class="btn-close box-content w-4 h-4 p-1 text-black border-none rounded-none opacity-50 focus:shadow-none focus:outline-none focus:opacity-100 hover:text-black hover:opacity-75 hover:no-underline"
          data-bs-dismiss="modal"
          aria-label="Close"
          data-mdb-ripple="true"
          data-mdb-ripple-duration="1000ms"
        />
      </div>
      <div class="modal-body relative p-4">
        <img class="modal_picture" src={meal.picture} alt={meal.alt} />
      </div>
      <div
        class="modal-footer flex flex-shrink-0 flex-wrap items-center justify-end p-4 border-t border-gray-200 rounded-b-md"
      >
        <button
          class="leading-tight rounded border p-1.5 border-zinc-700"
          type="button"
          data-bs-dismiss="modal">Close</button
        >
      </div>
    </div>
  </div>
</div>

<!-- //============================ Style ================================== -->
<style>
</style>
