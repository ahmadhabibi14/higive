<script lang="ts">
	import { Icon } from 'svelte-icons-pack';
	import {
		RiBusinessMailLine,
		RiDevicePhoneLine,
		RiLogosFacebookCircleLine,
		RiLogosInstagramLine,
		RiLogosTwitterXFill,
		RiLogosWhatsappLine,
		RiLogosYoutubeLine,
		RiMapMapPinRangeLine
	} from 'svelte-icons-pack/ri';

	const year: number = new Date().getFullYear();
</script>

<footer class="bg-istq text-istq-white flex flex-col pt-14 pb-8 px-6">
	<div class="container max-w-6xl mx-auto flex flex-col gap-5">
		<div class="w-full h-fit md:grid md:grid-cols-[3fr_1fr_2fr] flex flex-col gap-4">
			<div class="flex flex-col gap-4 items-start">
				<div class="flex flex-row gap-2 items-center">
					<img
						src="/icons/logo-text.png"
						alt="Pondok Yatim Istiqomah Logo"
						class="h-18 w-auto object-contain"
					/>
				</div>
				<p>
					Membina anak yatim dan dhuafa menjadi generasi Qur’ani yang berakhlak, mandiri, dan
					bermanfaat bagi umat.
				</p>
				<div class="flex flex-row gap-3 items-center" role="navigation">
					<a
						aria-label="Instagram"
						href="https://www.instagram.com/pondok_yatim_istiqomah"
						target="_blank"
						class="flex justify-center items-center p-2 rounded-full bg-white hover:bg-white/90 text-istq"
					>
						<Icon src={RiLogosInstagramLine} size="22" />
					</a>
					<a
						aria-label="Facebook"
						href="https://www.facebook.com/istiqomah"
						target="_blank"
						class="flex justify-center items-center p-2 rounded-full bg-white hover:bg-white/90 text-istq"
					>
						<Icon src={RiLogosFacebookCircleLine} size="22" />
					</a>
					<a
						aria-label="YouTube"
						href="https://www.youtube.com/channel/istiqomah"
						target="_blank"
						class="flex justify-center items-center p-2 rounded-full bg-white hover:bg-white/90 text-istq"
					>
						<Icon src={RiLogosYoutubeLine} size="22" />
					</a>
					<a
						aria-label="X (Twitter)"
						href="https://www.x.com/istiqomah"
						target="_blank"
						class="flex justify-center items-center p-2 rounded-full bg-white hover:bg-white/90 text-istq"
					>
						<Icon src={RiLogosTwitterXFill} size="19" />
					</a>
					<a
						aria-label="WhatsApp"
						href="https://wa.me/6281213339923"
						target="_blank"
						class="flex justify-center items-center p-2 rounded-full bg-white hover:bg-white/90 text-istq"
					>
						<Icon src={RiLogosWhatsappLine} size="22" />
					</a>
				</div>
			</div>
			<div class="flex flex-col gap-3 mt-4">
				<h4 class="text-lg text-qc-white font-semibold text-white">Navigation</h4>
				<nav class="flex flex-col gap-1">
					<a href="/profil" class="hover:underline hover:text-istq-green">Profil</a>
					<a href="/program" class="hover:underline hover:text-istq-green">Program</a>
					<a href="/layanan" class="hover:underline hover:text-istq-green">Layanan</a>
					<a href="/posts" class="hover:underline hover:text-istq-green">Artikel</a>
				</nav>
			</div>

			<div class="flex flex-col gap-3 mt-4">
				<h4 class="text-lg text-qc-white font-semibold text-white">Contact</h4>
				<div class="flex flex-col gap-1">
					<a
						href="https://maps.app.goo.gl/JHAMACgXWpHYZrKD8"
						target="_blank"
						class="flex flex-row gap-2 items-start hover:underline hover:text-istq-green"
					>
						<Icon
							size="20"
							className="text-istq-green fill-istq-green shrink-0"
							src={RiMapMapPinRangeLine}
						/>
						<p class="grow">
							Jl. Nangka III No. 47B, Perumahan Jatibening II Kel. Jatibening Baru, Kec. Pondokgede,
							Kota Bekasi
						</p>
					</a>
					<a
						href="mailto:pondokyatimistiqomah1@gmail.com"
						target="_blank"
						class="flex flex-row gap-2 items-center hover:underline hover:text-istq-green"
					>
						<Icon
							size="20"
							className="text-istq-green fill-istq-green shrink-0"
							src={RiBusinessMailLine}
						/>
						<p class="grow">pondokyatimistiqomah1@gmail.com</p>
					</a>
					<a
						href="tel:+6281213339923"
						class="flex flex-row gap-2 items-center hover:underline hover:text-istq-green"
					>
						<Icon
							size="20"
							className="text-istq-green fill-istq-green shrink-0"
							src={RiDevicePhoneLine}
						/>
						<p class="grow">(+62) 812-1333-9923</p>
					</a>
				</div>
			</div>
		</div>
		<div class="w-full border-t border-qc-white pt-8">
			<div class="text-qc-white flex flex-row items-center justify-center">
				<p class="">&copy; {year} Yayasan Pondok Yatim Istiqomah</p>
			</div>
		</div>
	</div>
</footer>
