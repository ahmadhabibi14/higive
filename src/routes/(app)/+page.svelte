<script lang="ts">
	import Head from '@/partials/Head.svelte';
	import FormDonasi from '@/partials/home/FormDonasi.svelte';
	import Paket from '@/partials/home/Paket.svelte';
	import { Icon } from 'svelte-icons-pack';
	import { RiBusinessGlobalLine, RiLogosInstagramLine } from 'svelte-icons-pack/ri';
</script>

<Head />

<div class="h-auto w-full flex flex-col max-w-full">
	<section class="relative h-[700px] overflow-hidden">
		<div class="absolute z-1 w-full h-auto">
			<svg
				preserveAspectRatio="xMidYMid slice"
				viewBox="0 0 1920 914"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M1167.08 881.434C772.811 953.869 224.748 888.751 0 847.137V0H1920V674.28C1845.23 710.635 1589.97 802.962 1167.08 881.434Z"
					fill="url(#paint0_linear_82_2)"
				/>
				<defs>
					<linearGradient
						id="paint0_linear_82_2"
						x1="6.35007e-06"
						y1="869"
						x2="2533"
						y2="-74.4999"
						gradientUnits="userSpaceOnUse"
					>
						<stop stop-color="#F9D53D" />
						<stop offset="0.6094" stop-color="#08B1A3" />
					</linearGradient>
				</defs>
			</svg>
		</div>
		<div
			class="h-[600px] overflow-hidden w-full
	flex flex-col gap-0 pb-20 absolute z-2"
		>
			<div class="flex flex-row justify-between">
				<div
					class="bg-white pt-6 pb-8 pl-10 pr-20 rounded-br-full
			h-fit w-fit"
				>
					<img src="/logo/logo-text.png" alt="Main Logo" class="h-16 w-auto object-contain" />
				</div>
				<div
					class="flex flex-col gap-0 pt-7 pr-10 justify-center items-center
			text-4xl text-white font-bold"
				>
					<span>Program</span>
					<span>Ramadhan</span>
					<span>1447 H</span>
				</div>
			</div>
			<div class="flex justify-center">
				<img src="/img/banner.png" alt="" class="h-[350px] w-auto" />
			</div>
		</div>
	</section>

	<section class="mt-20 mb-16 container max-w-5xl mx-auto">
		<div class="grid grid-cols-[40%_1fr] gap-6 items-center">
			<h2 class="text-5xl font-bold text-higive-primary text-center">
				Sedekah
				<br />Terbaik itu
				<br />di Bulan
				<br />Ramadhan
			</h2>
			<p class="text-higive-primary-2 text-4xl font-bold text-center">
				Rasulullah SAW bersabda: “Wahai Rasulullah, sedekah apakah yang paling utama?” Beliau
				menjawab, “Sedekah di bulan Ramadhan.” (HR. At-Tirmidzi)
			</p>
		</div>
	</section>

	<Paket />

	<FormDonasi />

	<section class="mt-10 bg-linear-to-b from-higive-secondary to-higive-primary py-10">
		<div class="container max-w-5xl mx-auto">
			<img src="/img/tf-donasi.png" alt="Donasi" class="w-full" />
			<div class="text-lg w-full mt-7 flex flex-row gap-7 justify-center items-center text-center">
				<a
					href="https://www.instagram.com/higiveindonesia"
					target="_blank"
					class="hover:underline text-white flex flex-row gap-2 items-center"
				>
					<div class="p-2 bg-white rounded-full">
						<Icon src={RiLogosInstagramLine} size="24" className="fill-higive-primary" />
					</div>
					<span>@higiveindonesia</span>
				</a>
				<a
					href="https://www.higive.id"
					target="_blank"
					class="hover:underline text-white flex flex-row gap-2 items-center"
				>
					<div class="p-2 bg-white rounded-full">
						<Icon src={RiBusinessGlobalLine} size="24" className="fill-higive-primary" />
					</div>
					<span>www.higive.id</span>
				</a>
			</div>
		</div>
	</section>
</div>
