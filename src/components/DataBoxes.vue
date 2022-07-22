<template>
  <div class="grid md:grid-cols-3 gap-12">
    <!-- Box 1 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Casos</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">Novos:</span>
        {{ numberWithDots(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithDots(stats.TotalConfirmed) }} 
      </div>
    </div>

    <!-- Box 2 -->
     <div class="shadow-md bg-blue-200 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Recuperados</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">Novos:</span>
        {{ numberWithDots(stats.NewRecovered) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithDots(stats.TotalRecovered) }}
      </div>
    
    <!-- Box 3 -->    
    </div>
    <div class="shadow-md bg-blue-300 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Mortes</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">Novas:</span>
        {{ numberWithDots(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithDots(stats.TotalDeaths) }}
      </div>
    </div>
    
  </div>

</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  setup () {
    return {
      numberWithDots(x) {
        return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, '.');
      }
    };
  }
};
</script>
