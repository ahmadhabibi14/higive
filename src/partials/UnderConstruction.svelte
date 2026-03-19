<script lang="ts">
	import { Icon } from 'svelte-icons-pack';
	import { LuConstruction } from 'svelte-icons-pack/lu';
</script>

<div
	class="bg-white text-gray-800 fixed top-0 bottom-0 left-0 right-0 h-screen w-screen overflow-x-hidden"
>
	<div class="w-full h-full flex flex-col">
		<main class="flex flex-col justify-center items-center left-0 right-0 b h-full">
			<div class="flex flex-col gap-7 px-5 md:px-0">
				<div>
					<Icon src={LuConstruction} size="150" className="stroke-higive-primary" />
				</div>
				<div class="flex flex-col gap-0">
					<h1 class="text-5xl md:text-6xl font-bold">Under Construction</h1>
					<p class="text-xl">
						Website dalam penangguhan sementara hingga proses administrasi selesai.
					</p>
				</div>
			</div>
		</main>
	</div>
</div>
