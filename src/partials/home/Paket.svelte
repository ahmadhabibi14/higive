<script lang="ts">
  const packets: {
    img: string;
    name: string;
    budget: string;
    id: string;
  }[] = [
    {
      id: 'buka',
      img: '/img/buka-puasa.png',
      name: 'Buka Puasa Santri Tahfidz Yatim Dhuafa',
      budget: 'Rp. 25.000.-/Paket'
    },
    {
      id: 'bingkisan',
      img: '/img/bingkisan.png',
      name: 'Bingkisan Lebaran Yatim Dhuafa',
      budget: 'Rp. 250.000.-/Paket'
    }
  ]
</script>

<section class="my-10 bg-linear-to-b from-higive-primary to-higive-secondary py-10">
	<div class="container max-w-5xl mx-auto grid grid-cols-2 gap-5">
    {#each packets as pk (pk.id)}
      <div class="flex flex-col items-center text-center justify-center
      gap-2 text-white">
        <img
        src={pk.img}
        alt={pk.name}
        class="h-52 w-auto object-contain"
        />
        <h3 class="text-4xl font-bold">{pk.name}</h3>
        <span class="text-2xl font-bold bg-higive-primary py-2 px-4 rounded-xl">
          {pk.budget}
        </span>
      </div>
    {/each}
  </div>
</section>
