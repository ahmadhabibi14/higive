<script lang="ts">
	import { SiteName, SiteDesc, SiteBaseUrl, SiteImageUrl, SiteAuthor } from '@/lib/constant';

	export let title: string = SiteName;
	export let path: string = '';
	export let description: string = SiteDesc;
	export let imageUrl: string = SiteImageUrl;
	export let author: string = SiteAuthor;
	export let imgWidth: string = '1200';
	export let imgHeight: string = '630';

	const siteUrl: string = SiteBaseUrl + path;
</script>

<svelte:head>
	<title>{title}</title>
	<meta http-equiv="x-ua-compatible" content="ie=edge" />
	<meta name="author" content={author} />
	<meta name="description" content={description} />
	<meta name="referrer" content="no-referrer-when-downgrade" />

	<meta property="og:site_name" content={title} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:locale" content="id_ID" />
	<meta property="og:locale:alternate" content="en_UK" />
	<meta property="og:locale:alternate" content="ms_MY" />
	<meta property="og:type" content="website" />
	<meta property="og:url" content={siteUrl} />
	<meta property="og:image" content={imageUrl ? imageUrl : SiteImageUrl} />
	<meta property="og:image:secure_url" content={imageUrl ? imageUrl : SiteImageUrl} />
	<meta property="og:image:width" content={imgWidth} />
	<meta property="og:image:height" content={imgHeight} />
	<meta property="og:image:alt" content={title} />
	<meta property="og:see_also" content="https://www.instagram.com/higiveindonesia" />

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:image" content={imageUrl} />
	<meta name="twitter:image:width" content={imgWidth} />
	<meta name="twitter:image:height" content={imgHeight} />

	<meta name="DC.title" content="Geo Tag Generator" />
	<meta name="geo.region" content="ID-JK" />
	<meta name="geo.placename" content="Jakarta Timur, DKI Jakarta" />
	<meta name="geo.position" content="-6.333851, 106.902487" />
	<meta name="ICBM" content="-6.333851, 106.902487" />

	<link href={SiteBaseUrl} rel="canonical" />
	<link href={SiteBaseUrl} rel="home" />
	<link type="text/plain" href="{SiteBaseUrl}/humans.txt" rel="author" />

	<!-- Facebook Pixel Code -->
	<script>
		!(function (f, b, e, v, n, t, s) {
			if (f.fbq) return;
			n = f.fbq = function () {
				n.callMethod ? n.callMethod.apply(n, arguments) : n.queue.push(arguments);
			};
			if (!f._fbq) f._fbq = n;
			n.push = n;
			n.loaded = !0;
			n.version = '2.0';
			n.queue = [];
			t = b.createElement(e);
			t.async = !0;
			t.src = v;
			s = b.getElementsByTagName(e)[0];
			s.parentNode.insertBefore(t, s);
		})(window, document, 'script', 'https://connect.facebook.net/en_US/fbevents.js');
		fbq('init', '729791029428975');
		fbq('track', 'PageView');
	</script>
	<noscript>
		<img
			alt="Facebook Pixel Tracking"
			height="1"
			width="1"
			style="display:none"
			src="https://www.facebook.com/tr?id=729791029428975&ev=PageView&noscript=1"
		/>
	</noscript>
	<!-- End Facebook Pixel Code -->
</svelte:head>
