<script lang="ts">
	// form donasi
	let namaLengkap: string = $state('');
	let alamat: string = $state('');
	let noTelepon: string = $state('');
	let nominalDonasi: number = $state(100000);

	const programOpor: string = 'Opor dan Ketupat Lebaran Santri Lapas';
	const programBingkisan: string = "Bingkisan Lebaran Yatim dan Dhu'afa";

	type ProgramId = 'opor' | 'bingkisan';
	const idProgramOpor: ProgramId = 'opor';
	const idProgramBingkisan: ProgramId = 'bingkisan';

	let program: { id: ProgramId; name: string }[] = [];

	let oporKetupat: boolean = $state(false);
	let bingkisan: boolean = $state(false);

	const handleSubmit = () => {
		console.log('program:', program);
		if (!namaLengkap || !alamat || !noTelepon || program.length === 0 || !nominalDonasi) {
			alert('Mohon lengkapi semua field sebelum mengirim donasi.');
			return;
		}

		let textToWhatsApp = `Nama: ${namaLengkap}
Alamat: ${alamat}
No. Telepon: ${noTelepon}
Program: ${program.map((p) => p.name).join(', ')}
Nominal Donasi: Rp. ${nominalDonasi.toLocaleString('id-ID')}`;

		window.open(`https://wa.me/6285119903605?text=${encodeURIComponent(textToWhatsApp)}`, '_blank');
	};
</script>

<section class="container max-w-5xl mx-auto">
	<div class="flex flex-col gap-6 md:w-8/12 w-full mx-auto">
		<div class="flex justify-center items-center">
			<div
				class="text-5xl font-bold text-center w-fit
		bg-higive-secondary text-white py-2 px-6 rounded-lg
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
				<div class="h-fit bg-higive-primary text-white py-3 px-4 px-auto rounded-xl text-center">
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
							} else {
								program = program.filter((p) => p.id !== idProgramOpor);
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
							} else {
								program = program.filter((p) => p.id !== idProgramBingkisan);
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
				<label for="nominal" class="text-sm ml-2 text-gray-600">Nominal Donasi</label>
				<input
					id="nominal"
					placeholder="100000"
					type="number"
					bind:value={nominalDonasi}
					class="bg-higive-primary caret-higive-secondary text-white placeholder-gray-200
				py-3 px-4 rounded-xl focus:outline-gray-300 focus:ring-2 focus:outline-2"
				/>
			</div>
			<button
				onclick={handleSubmit}
				class="bg-higive-secondary text-white
       py-2 px-auto rounded-xl hover:bg-higive-secondary/90 focus:outline-none
       focus:ring-2 focus:ring-higive-secondary focus:ring-offset-2 w-full text-lg font-bold
       cursor-pointer flex items-center justify-center mt-7"
			>
				<span>Kirim Donasi</span>
			</button>
		</div>
	</div>
</section>
