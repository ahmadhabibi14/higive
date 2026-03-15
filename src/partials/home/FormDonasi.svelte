<script lang="ts">
	import toast, { Toaster } from 'svelte-french-toast';
	import { Icon } from 'svelte-icons-pack';
	import { RiFinanceExchangeLine } from 'svelte-icons-pack/ri';

	// form donasi
	let namaLengkap: string = $state('');
	let alamat: string = $state('');
	let noTelepon: string = $state('');
	let nominalDonasi: number = $state(0);

	const programOpor: string = 'Opor dan Ketupat Lebaran Santri Lapas';
	const programBingkisan: string = "Bingkisan Lebaran Yatim dan Dhu'afa";
	const nominalOpor: number = 30000;
	const nominalBingkisan: number = 250000;

	type ProgramId = 'opor' | 'bingkisan';
	const idProgramOpor: ProgramId = 'opor';
	const idProgramBingkisan: ProgramId = 'bingkisan';

	let program: { id: ProgramId; name: string }[] = [];

	let oporKetupat: boolean = $state(false);
	let bingkisan: boolean = $state(false);

	const noRekBSI: string = 'Rek BSI 8370000124';
	const noRekMandiri: string = 'Rek Mandiri 4270000124';

	let rekening: string = $state(noRekBSI);
	let checkedRekBSI: boolean = $state(true);
	let checkedRekMandiri: boolean = $state(false);

	let nominalTambahan: number = $state(0);

	let totalDonasi = $derived(nominalDonasi + nominalTambahan);

	const handleSubmit = () => {
		if (
			!namaLengkap ||
			!alamat ||
			!noTelepon ||
			program.length === 0 ||
			!nominalDonasi ||
			nominalDonasi <= 0
		) {
			toast.error('Mohon lengkapi semua form sebelum mengirim donasi.');
			return;
		}

		let textToWhatsApp = `Nama: ${namaLengkap}
Alamat: ${alamat}
No. Telepon: ${noTelepon}
Program: ${program.map((p) => p.name).join(', ')}
Nominal Donasi: Rp. ${nominalDonasi.toLocaleString('id-ID')}
Nominal Tambahan: Rp. ${nominalTambahan.toLocaleString('id-ID')}
Total Donasi: Rp. ${(nominalDonasi + nominalTambahan).toLocaleString('id-ID')}
Rekening Tujuan: ${rekening}`;

		window.open(`https://wa.me/6285119903605?text=${encodeURIComponent(textToWhatsApp)}`, '_blank');
	};
</script>

<Toaster />

<section class="container max-w-5xl mx-auto">
	<div class="flex flex-col gap-6 md:w-8/12 w-full mx-auto px-4 md:px-0">
		<div class="flex justify-center items-center">
			<div
				class="text-4xl md:text-5xl font-bold text-center w-fit
		bg-higive-secondary text-higive-black py-2 px-6 rounded-lg
		flex items-center justify-center"
			>
				<span>Form Donasi</span>
			</div>
		</div>
		<div class="flex flex-col gap-2">
			<div class="flex flex-col gap-1.5 w-full">
				<label for="nama" class="text-sm ml-2 text-gray-600">Nama Lengkap</label>
				<input
					id="nama"
					placeholder="Muhammad"
					bind:value={namaLengkap}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="alamat" class="text-sm ml-2 text-gray-600">Alamat</label>
				<input
					id="alamat"
					placeholder="Jl. Raya No. 123"
					bind:value={alamat}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="telepon" class="text-sm ml-2 text-gray-600">No. Telepon</label>
				<input
					id="telepon"
					placeholder="081234567890"
					type="number"
					bind:value={noTelepon}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<div class="grid grid-cols-2 w-full gap-5 mt-6 mb-3">
				<div
					class="h-fit bg-higive-secondary
				text-higive-black py-3 px-4 px-auto rounded-xl text-center font-semibold"
				>
					<span>Pilh Program</span>
				</div>
				<div class="w-full flex flex-col gap-3">
					<button
						onclick={() => {
							oporKetupat = !oporKetupat;
							if (oporKetupat) {
								program.push({
									id: idProgramOpor,
									name: programOpor
								});
								nominalDonasi += nominalOpor;
							} else {
								program = program.filter((p) => p.id !== idProgramOpor);
								if (nominalDonasi >= nominalOpor) {
									nominalDonasi -= nominalOpor;
								}
							}
						}}
						class="cursor-pointer h-fit hover:bg-higive-primary-2 bg-higive-primary text-white
						py-3 px-4 px-auto rounded-xl text-center
						{oporKetupat ? 'outline-4 outline-higive-secondary' : ''}"
					>
						<span>Opor dan Ketupat Lebaran Santri Lapas</span>
					</button>
					<button
						onclick={() => {
							bingkisan = !bingkisan;
							if (bingkisan) {
								program.push({
									id: idProgramBingkisan,
									name: programBingkisan
								});
								nominalDonasi += nominalBingkisan;
							} else {
								program = program.filter((p) => p.id !== idProgramBingkisan);
								if (nominalDonasi >= nominalBingkisan) {
									nominalDonasi -= nominalBingkisan;
								}
							}
						}}
						class="cursor-pointer h-fit hover:bg-higive-primary-2 bg-higive-primary text-white
						py-3 px-4 px-auto rounded-xl text-center
						{bingkisan ? 'outline-4 outline-higive-secondary' : ''}"
					>
						<span>Bingkisan Lebaran Yatim dan Dhu'afa</span>
					</button>
				</div>
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="nominal" class="text-sm ml-2 text-gray-600"
					>Nominal Donasi <span class="text-xs text-higive-primary">*(otomatis)</span></label
				>
				<input
					disabled
					id="nominal"
					placeholder="100000"
					type="number"
					bind:value={nominalDonasi}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="nominalTambahan" class="text-sm ml-2 text-gray-600">Nominal Tambahan</label>
				<input
					id="nominalTambahan"
					placeholder="100000"
					type="number"
					bind:value={nominalTambahan}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<div class="text-lg mt-5">
				<span>Total Donasi: Rp. {totalDonasi.toLocaleString('id-ID')}</span>
			</div>

			<div class="grid grid-cols-2 w-full gap-5 mt-6 mb-3">
				<div
					class="h-fit bg-higive-secondary
				text-higive-black font-semibold py-3 px-4 px-auto rounded-xl text-center"
				>
					<span>Pilh Rekening</span>
				</div>
				<div class="w-full flex flex-col gap-3">
					<button
						onclick={() => {
							checkedRekBSI = true;
							checkedRekMandiri = false;
							rekening = noRekBSI;
						}}
						class="cursor-pointer h-fit hover:bg-higive-primary-2 bg-higive-primary text-white
						py-3 px-4 px-auto rounded-xl text-center
						{checkedRekBSI ? 'outline-4 outline-higive-secondary' : ''}"
					>
						<span>{noRekBSI}</span>
					</button>
					<button
						onclick={() => {
							checkedRekBSI = false;
							checkedRekMandiri = true;
							rekening = noRekMandiri;
						}}
						class="cursor-pointer h-fit hover:bg-higive-primary-2 bg-higive-primary text-white
						py-3 px-4 px-auto rounded-xl text-center
						{checkedRekMandiri ? 'outline-4 outline-higive-secondary' : ''}"
					>
						<span>{noRekMandiri}</span>
					</button>
				</div>
			</div>
			<button
				onclick={handleSubmit}
				class="bg-higive-secondary text-higive-black
       py-3 px-auto rounded-xl hover:bg-higive-secondary/90 focus:outline-none
       focus:ring-2 focus:ring-higive-secondary focus:ring-offset-2 w-full text-lg font-bold
       cursor-pointer flex items-center justify-center mt-7 gap-2"
			>
				<Icon src={RiFinanceExchangeLine} size="24" className="-mt-1" />
				<span>Kirim Donasi</span>
			</button>
		</div>
	</div>
</section>
