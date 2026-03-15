<script lang="ts">
	const packets: {
		img: string;
		name: string;
		budget: string;
		id: string;
	}[] = [
		{
			id: 'buka',
			img: '/img/opor-ketupat.png',
			name: 'Opor dan Ketupat Lebaran Santri Lapas',
			budget: 'Rp. 30.000.-/Porsi'
		},
		{
			id: 'bingkisan',
			img: '/img/bingkisan.png',
			name: 'Bingkisan Lebaran untuk Yatim Dhuafa',
			budget: 'Rp. 250.000.-/Paket'
		}
	];
</script>

<section class="my-10">
	<div class="w-full h-auto -mb-1">
		<svg viewBox="0 0 1440 160" fill="none" xmlns="http://www.w3.org/2000/svg">
			<path
				d="M0 128.058L48 112.086C96 96.1151 192 64.1726 288 37.5206C384 11.2679 480 -10.6926 576 5.57812C672 21.2499 768 75.1528 864 90.8246C960 107.095 1056 85.1348 1152 90.8246C1248 96.1151 1344 128.058 1392 144.029L1440 160H1392C1344 160 1248 160 1152 160C1056 160 960 160 864 160C768 160 672 160 576 160C480 160 384 160 288 160C192 160 96 160 48 160H0V128.058Z"
				fill="#00B0A6"
			/>
		</svg>
	</div>
	<div
		class="md:bg-[radial-gradient(circle_at_center,#00B0A6,#00B0A6)] bg-[radial-gradient(circle_at_center,#F9D43C,#00B0A6,#00B0A6)] md:py-14 pt-8 pb-14"
	>
		<div class="container max-w-5xl mx-auto grid grid-cols-2 gap-5 px-5 md:px-0">
			{#each packets as pk (pk.id)}
				<div
					class="flex flex-col items-center text-center justify-center
      md:gap-2 gap-0 text-white"
				>
					<img src={pk.img} alt={pk.name} class="h-60 w-auto object-contain md:mb-3" />
					<div class="flex flex-col gap-2">
						<h3 class="text-2xl md:text-4xl font-bold leading-7 md:leading-9">{pk.name}</h3>
						<span
							class="text-sm md:text-2xl font-bold bg-higive-primary
				md:py-2 py-1.5 md:px-4 px-3 rounded-xl w-fit h-fit mx-auto"
						>
							{pk.budget}
						</span>
					</div>
				</div>
			{/each}
		</div>
	</div>
	<div class="w-full h-auto">
		<svg viewBox="0 0 1440 145" fill="none" xmlns="http://www.w3.org/2000/svg">
			<path
				d="M0 64L48 85.3C96 107 192 149 288 144C384 139 480 85 576 85.3C672 85 768 139 864 144C960 149 1056 107 1152 90.7C1248 75 1344 85 1392 90.7L1440 96V0H1392C1344 0 1248 0 1152 0C1056 0 960 0 864 0C768 0 672 0 576 0C480 0 384 0 288 0C192 0 96 0 48 0H0V64Z"
				fill="#00B0A6"
			/>
		</svg>
	</div>
</section>
