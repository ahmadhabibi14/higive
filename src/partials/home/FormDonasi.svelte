<script lang="ts">
	import { Input } from "@/lib/components/ui/input";

	// form donasi
	// nama lengkap
	// alamat
	// no telepon
	// pilih program: buka puasa, bingkisan lebaran

	// nominal donasi
	// submit
</script>

<section class="container max-w-5xl mx-auto">
	<div class="flex flex-col gap-6 md:w-6/12 w-full mx-auto">
		<h3 class="text-5xl font-bold text-center">Form Donasi</h3>
		<div class="flex flex-col gap-2">
			<div class="flex flex-col gap-1.5 w-full">
				<label for="nama" class="text-sm">Nama Lengkap</label>
				<Input id="nama" placeholder="Muhammad Ali" />
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="alamat" class="text-sm">Alamat</label>
				<Input id="alamat" placeholder="Jl. Raya No. 123" />
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="telepon" class="text-sm">No. Telepon</label>
				<Input id="telepon" placeholder="081234567890" />
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="program" class="text-sm">Pilih Program</label>
				<select id="program" class="border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500">
					<option value="">-- Pilih Program --</option>
					<option value="buka-puasa">Buka Puasa</option>
					<option value="bingkisan-lebaran">Bingkisan Lebaran</option>
				</select>
			</div>
			<div class="flex flex-col gap-1.5 w-full">
				<label for="nominal" class="text-sm">Nominal Donasi</label>
				<Input id="nominal" placeholder="Rp 100.000" />
			</div>
			<button class="bg-higive-primary text-white
       py-2 px-auto rounded-md hover:bg-higive-primary-dark focus:outline-none
       focus:ring-2 focus:ring-higive-primary focus:ring-offset-2 w-full text-lg font-bold
       cursor-pointer flex items-center justify-center">
				<span>Kirim Donasi</span>
			</button>
		</div>
	</div>
</section>
