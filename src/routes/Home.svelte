<!-- //============================ Script ================================= -->
<script>
  import MealCard from "../components/MealCard.svelte";
  import { meals } from "../mealDatas";
</script>

<!-- //============================ HTML =================================== -->
<div
  class="flex flex-col justify-center text-center mx-auto max-w-none bg-[url('/img/home.webp')] bg-no-repeat bg-cover bg-left h-80"
>
  <div
    class="flex flex-col justify-center m-4 md:m-20   bg-black opacity-75 rounded-md"
  >
    <h1 class="text-white text-4xl md:text-8xl font-light pt-10 pb-10">Home</h1>
    <p class="md:text-base text-center text-white mb-4 leading-tight">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut nobis
      nesciunt suscipit vel quam consectetur consequuntur nemo.
    </p>
  </div>
</div>
<div
  class="meal_container ml-0 mr-0 md:ml-8 md:mr-8 lg:ml-8 lg:mr-8 xl:ml-8 xl:mr-8"
>
  <div class="mt-8 mb-8">
    <h2 class="text-center text-white text-2xl md:text-6xl font-thin ">
      La <span class="text-4xl md:text-7xl font-thin">Carte</span>
    </h2>
  </div>
  <div
    class="meal_grid grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 justify-center"
  >
    {#each meals as meal}
      <MealCard {meal} />
    {/each}
  </div>
</div>

<!-- //============================ Style ================================== -->
<style>
  h1 {
    font-weight: 300;
    font-size: 5rem;
  }
</style>
