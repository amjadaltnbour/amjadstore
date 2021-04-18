
<!DOCTYPE html>
<!--[if IE 9 ]> <html lang="en-US" class="ie9 loading-site no-js"> <![endif]-->
<!--[if IE 8 ]> <html lang="en-US" class="ie8 loading-site no-js"> <![endif]-->
<!--[if (gte IE 9)|!(IE)]><!--><html lang="en-US" class="loading-site no-js"> <!--<![endif]-->
<head>
	<meta charset="UTF-8" />
	<link rel="profile" href="http://gmpg.org/xfn/11" />
	<link rel="pingback" href="http://127.0.0.1:82/wordpress/xmlrpc.php" />

					<script>document.documentElement.className = document.documentElement.className + ' yes-js js_active js'</script>
			<script>(function(html){html.className = html.className.replace(/\bno-js\b/,'js')})(document.documentElement);</script>
<title>admim&#039;s Blog! &#8211; Just another WordPress site</title>
<meta name='robots' content='max-image-preview:large' />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" /><link rel='dns-prefetch' href='//fonts.googleapis.com' />
<link rel='dns-prefetch' href='//s.w.org' />
<link rel="alternate" type="application/rss+xml" title="admim&#039;s Blog! &raquo; Feed" href="http://127.0.0.1:82/wordpress/?feed=rss2" />
<link rel="alternate" type="application/rss+xml" title="admim&#039;s Blog! &raquo; Comments Feed" href="http://127.0.0.1:82/wordpress/?feed=comments-rss2" />
		<script type="text/javascript">
			window._wpemojiSettings = {"baseUrl":"https:\/\/s.w.org\/images\/core\/emoji\/13.0.1\/72x72\/","ext":".png","svgUrl":"https:\/\/s.w.org\/images\/core\/emoji\/13.0.1\/svg\/","svgExt":".svg","source":{"wpemoji":"http:\/\/127.0.0.1:82\/wordpress\/wp-includes\/js\/wp-emoji.js?ver=5.7.1","twemoji":"http:\/\/127.0.0.1:82\/wordpress\/wp-includes\/js\/twemoji.js?ver=5.7.1"}};
			/**
 * @output wp-includes/js/wp-emoji-loader.js
 */

( function( window, document, settings ) {
	var src, ready, ii, tests;

	// Create a canvas element for testing native browser support of emoji.
	var canvas = document.createElement( 'canvas' );
	var context = canvas.getContext && canvas.getContext( '2d' );

	/**
	 * Checks if two sets of Emoji characters render the same visually.
	 *
	 * @since 4.9.0
	 *
	 * @private
	 *
	 * @param {number[]} set1 Set of Emoji character codes.
	 * @param {number[]} set2 Set of Emoji character codes.
	 *
	 * @return {boolean} True if the two sets render the same.
	 */
	function emojiSetsRenderIdentically( set1, set2 ) {
		var stringFromCharCode = String.fromCharCode;

		// Cleanup from previous test.
		context.clearRect( 0, 0, canvas.width, canvas.height );
		context.fillText( stringFromCharCode.apply( this, set1 ), 0, 0 );
		var rendered1 = canvas.toDataURL();

		// Cleanup from previous test.
		context.clearRect( 0, 0, canvas.width, canvas.height );
		context.fillText( stringFromCharCode.apply( this, set2 ), 0, 0 );
		var rendered2 = canvas.toDataURL();

		return rendered1 === rendered2;
	}

	/**
	 * Detects if the browser supports rendering emoji or flag emoji.
	 *
	 * Flag emoji are a single glyph made of two characters, so some browsers
	 * (notably, Firefox OS X) don't support them.
	 *
	 * @since 4.2.0
	 *
	 * @private
	 *
	 * @param {string} type Whether to test for support of "flag" or "emoji".
	 *
	 * @return {boolean} True if the browser can render emoji, false if it cannot.
	 */
	function browserSupportsEmoji( type ) {
		var isIdentical;

		if ( ! context || ! context.fillText ) {
			return false;
		}

		/*
		 * Chrome on OS X added native emoji rendering in M41. Unfortunately,
		 * it doesn't work when the font is bolder than 500 weight. So, we
		 * check for bold rendering support to avoid invisible emoji in Chrome.
		 */
		context.textBaseline = 'top';
		context.font = '600 32px Arial';

		switch ( type ) {
			case 'flag':
				/*
				 * Test for Transgender flag compatibility. This flag is shortlisted for the Emoji 13 spec,
				 * but has landed in Twemoji early, so we can add support for it, too.
				 *
				 * To test for support, we try to render it, and compare the rendering to how it would look if
				 * the browser doesn't render it correctly (white flag emoji + transgender symbol).
				 */
				isIdentical = emojiSetsRenderIdentically(
					[ 0x1F3F3, 0xFE0F, 0x200D, 0x26A7, 0xFE0F ],
					[ 0x1F3F3, 0xFE0F, 0x200B, 0x26A7, 0xFE0F ]
				);

				if ( isIdentical ) {
					return false;
				}

				/*
				 * Test for UN flag compatibility. This is the least supported of the letter locale flags,
				 * so gives us an easy test for full support.
				 *
				 * To test for support, we try to render it, and compare the rendering to how it would look if
				 * the browser doesn't render it correctly ([U] + [N]).
				 */
				isIdentical = emojiSetsRenderIdentically(
					[ 0xD83C, 0xDDFA, 0xD83C, 0xDDF3 ],
					[ 0xD83C, 0xDDFA, 0x200B, 0xD83C, 0xDDF3 ]
				);

				if ( isIdentical ) {
					return false;
				}

				/*
				 * Test for English flag compatibility. England is a country in the United Kingdom, it
				 * does not have a two letter locale code but rather an five letter sub-division code.
				 *
				 * To test for support, we try to render it, and compare the rendering to how it would look if
				 * the browser doesn't render it correctly (black flag emoji + [G] + [B] + [E] + [N] + [G]).
				 */
				isIdentical = emojiSetsRenderIdentically(
					[ 0xD83C, 0xDFF4, 0xDB40, 0xDC67, 0xDB40, 0xDC62, 0xDB40, 0xDC65, 0xDB40, 0xDC6E, 0xDB40, 0xDC67, 0xDB40, 0xDC7F ],
					[ 0xD83C, 0xDFF4, 0x200B, 0xDB40, 0xDC67, 0x200B, 0xDB40, 0xDC62, 0x200B, 0xDB40, 0xDC65, 0x200B, 0xDB40, 0xDC6E, 0x200B, 0xDB40, 0xDC67, 0x200B, 0xDB40, 0xDC7F ]
				);

				return ! isIdentical;
			case 'emoji':
				/*
				 * So easy, even a baby could do it!
				 *
				 *  To test for Emoji 13 support, try to render a new emoji: Man Feeding Baby.
				 *
				 * The Man Feeding Baby emoji is a ZWJ sequence combining 👨 Man, a Zero Width Joiner and 🍼 Baby Bottle.
				 *
				 * 0xD83D, 0xDC68 == Man emoji.
				 * 0x200D == Zero-Width Joiner (ZWJ) that links the two code points for the new emoji or
				 * 0x200B == Zero-Width Space (ZWS) that is rendered for clients not supporting the new emoji.
				 * 0xD83C, 0xDF7C == Baby Bottle.
				 *
				 * When updating this test for future Emoji releases, ensure that individual emoji that make up the
				 * sequence come from older emoji standards.
				 */
				isIdentical = emojiSetsRenderIdentically(
					[0xD83D, 0xDC68, 0x200D, 0xD83C, 0xDF7C],
					[0xD83D, 0xDC68, 0x200B, 0xD83C, 0xDF7C]
				);

				return ! isIdentical;
		}

		return false;
	}

	/**
	 * Adds a script to the head of the document.
	 *
	 * @ignore
	 *
	 * @since 4.2.0
	 *
	 * @param {Object} src The url where the script is located.
	 * @return {void}
	 */
	function addScript( src ) {
		var script = document.createElement( 'script' );

		script.src = src;
		script.defer = script.type = 'text/javascript';
		document.getElementsByTagName( 'head' )[0].appendChild( script );
	}

	tests = Array( 'flag', 'emoji' );

	settings.supports = {
		everything: true,
		everythingExceptFlag: true
	};

	/*
	 * Tests the browser support for flag emojis and other emojis, and adjusts the
	 * support settings accordingly.
	 */
	for( ii = 0; ii < tests.length; ii++ ) {
		settings.supports[ tests[ ii ] ] = browserSupportsEmoji( tests[ ii ] );

		settings.supports.everything = settings.supports.everything && settings.supports[ tests[ ii ] ];

		if ( 'flag' !== tests[ ii ] ) {
			settings.supports.everythingExceptFlag = settings.supports.everythingExceptFlag && settings.supports[ tests[ ii ] ];
		}
	}

	settings.supports.everythingExceptFlag = settings.supports.everythingExceptFlag && ! settings.supports.flag;

	// Sets DOMReady to false and assigns a ready function to settings.
	settings.DOMReady = false;
	settings.readyCallback = function() {
		settings.DOMReady = true;
	};

	// When the browser can not render everything we need to load a polyfill.
	if ( ! settings.supports.everything ) {
		ready = function() {
			settings.readyCallback();
		};

		/*
		 * Cross-browser version of adding a dom ready event.
		 */
		if ( document.addEventListener ) {
			document.addEventListener( 'DOMContentLoaded', ready, false );
			window.addEventListener( 'load', ready, false );
		} else {
			window.attachEvent( 'onload', ready );
			document.attachEvent( 'onreadystatechange', function() {
				if ( 'complete' === document.readyState ) {
					settings.readyCallback();
				}
			} );
		}

		src = settings.source || {};

		if ( src.concatemoji ) {
			addScript( src.concatemoji );
		} else if ( src.wpemoji && src.twemoji ) {
			addScript( src.twemoji );
			addScript( src.wpemoji );
		}
	}

} )( window, document, window._wpemojiSettings );
		</script>
		<style type="text/css">
img.wp-smiley,
img.emoji {
	display: inline !important;
	border: none !important;
	box-shadow: none !important;
	height: 1em !important;
	width: 1em !important;
	margin: 0 .07em !important;
	vertical-align: -0.1em !important;
	background: none !important;
	padding: 0 !important;
}
</style>
	<link rel='stylesheet' id='dashicons-css'  href='http://127.0.0.1:82/wordpress/wp-includes/css/dashicons.css?ver=5.7.1' type='text/css' media='all' />
<style id='dashicons-inline-css' type='text/css'>
[data-font="Dashicons"]:before {font-family: 'Dashicons' !important;content: attr(data-icon) !important;speak: none !important;font-weight: normal !important;font-variant: normal !important;text-transform: none !important;line-height: 1 !important;font-style: normal !important;-webkit-font-smoothing: antialiased !important;-moz-osx-font-smoothing: grayscale !important;}
</style>
<link rel='stylesheet' id='admin-bar-css'  href='http://127.0.0.1:82/wordpress/wp-includes/css/admin-bar.css?ver=5.7.1' type='text/css' media='all' />
<link rel='stylesheet' id='wp-block-library-css'  href='http://127.0.0.1:82/wordpress/wp-includes/css/dist/block-library/style.css?ver=5.7.1' type='text/css' media='all' />
<link rel='stylesheet' id='wc-block-vendors-style-css'  href='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/packages/woocommerce-blocks/build/vendors-style.css?ver=1618613988' type='text/css' media='all' />
<link rel='stylesheet' id='wc-block-style-css'  href='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/packages/woocommerce-blocks/build/style.css?ver=1618613988' type='text/css' media='all' />
<link rel='stylesheet' id='contact-form-7-css'  href='http://127.0.0.1:82/wordpress/wp-content/plugins/contact-form-7/includes/css/styles.css?ver=5.4' type='text/css' media='all' />
<style id='woocommerce-inline-inline-css' type='text/css'>
.woocommerce form .form-row .required { visibility: visible; }
</style>
<link rel='stylesheet' id='jquery-selectBox-css'  href='http://127.0.0.1:82/wordpress/wp-content/plugins/yith-woocommerce-wishlist/assets/css/jquery.selectBox.css?ver=1.2.0' type='text/css' media='all' />
<link rel='stylesheet' id='flatsome-icons-css'  href='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/css/fl-icons.css?ver=3.12' type='text/css' media='all' />
<link rel='stylesheet' id='flatsome-woocommerce-wishlist-css'  href='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/inc/integrations/wc-yith-wishlist/wishlist.css?ver=3.10.2' type='text/css' media='all' />
<link rel='stylesheet' id='uwa-front-css-css'  href='http://127.0.0.1:82/wordpress/wp-content/plugins/ultimate-woocommerce-auction/assets/css/uwa-front.css?ver=2.1.4' type='text/css' media='' />
<link rel='stylesheet' id='flatsome-main-css'  href='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/css/flatsome.css?ver=3.13.3' type='text/css' media='all' />
<link rel='stylesheet' id='flatsome-shop-css'  href='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/css/flatsome-shop.css?ver=3.13.3' type='text/css' media='all' />
<link rel='stylesheet' id='flatsome-style-css'  href='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome-child/style.css?ver=3.0' type='text/css' media='all' />
<link rel='stylesheet' id='flatsome-googlefonts-css'  href='//fonts.googleapis.com/css?family=Tajawal%3Aregular%2C700%2Cregular%2C700%7CCairo%3Aregular%2Cregular&#038;display=swap&#038;ver=3.9' type='text/css' media='all' />
<script type="text/javascript">(function(a,d){if(a._nsl===d){a._nsl=[];var c=function(){if(a.jQuery===d)setTimeout(c,33);else{for(var b=0;b<a._nsl.length;b++)a._nsl[b].call(a,a.jQuery);a._nsl={push:function(b){b.call(a,a.jQuery)}}}};c()}})(window);</script><script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/jquery/jquery.js?ver=3.5.1' id='jquery-core-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/jquery/jquery-migrate.js?ver=3.3.2' id='jquery-migrate-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/ultimate-woocommerce-auction/assets/js/jquery.countdown.min.js?ver=2.1.4' id='uwa-jquery-countdown-js'></script>
<script type='text/javascript' id='uwa-jquery-countdown-multi-lang-js-extra'>
/* <![CDATA[ */
var multi_lang_data = {"labels":{"Years":"Years","Months":"Months","Weeks":"Weeks","Days":"Days","Hours":"Hours","Minutes":"Minutes","Seconds":"Seconds"},"labels1":{"Year":"Year","Month":"Month","Week":"Week","Day":"Day","Hour":"Hour","Minute":"Minute","Second":"Second"},"compactLabels":{"y":"y","m":"m","w":"w","d":"d"}};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/ultimate-woocommerce-auction/assets/js/jquery.countdown-multi-lang.js?ver=2.1.4' id='uwa-jquery-countdown-multi-lang-js'></script>
<script type='text/javascript' id='uwa-front-js-extra'>
/* <![CDATA[ */
var uwa_data = {"expired":"Auction has Expired!","gtm_offset":"0","started":"Auction Started! Please refresh page.","outbid_message":"","hide_compact":"no","refresh_interval":"1"};
var WpUat = {"calendar_icon":"<i class=\"dashicons-calendar-alt\"><\/i>"};
var WooUa = {"ajaxurl":"http:\/\/127.0.0.1:82\/wordpress\/wp-admin\/admin-ajax.php","ua_nonce":"3ea64792b9","last_timestamp":"1618528623","calendar_image":"http:\/\/127.0.0.1:82\/wordpress\/wp-content\/plugins\/woocommerce\/assets\/images\/calendar.png"};
var UWA_Ajax_Qry = {"ajaqry":"\/wordpress\/?uwa-ajax"};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/ultimate-woocommerce-auction/assets/js/uwa-front.js?ver=2.1.4' id='uwa-front-js'></script>
<link rel="https://api.w.org/" href="http://127.0.0.1:82/wordpress/index.php?rest_route=/" /><link rel="alternate" type="application/json" href="http://127.0.0.1:82/wordpress/index.php?rest_route=/wp/v2/pages/696" /><link rel="EditURI" type="application/rsd+xml" title="RSD" href="http://127.0.0.1:82/wordpress/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="http://127.0.0.1:82/wordpress/wp-includes/wlwmanifest.xml" /> 
<meta name="generator" content="WordPress 5.7.1" />
<meta name="generator" content="WooCommerce 5.2.2" />
<link rel="canonical" href="http://127.0.0.1:82/wordpress/" />
<link rel='shortlink' href='http://127.0.0.1:82/wordpress/' />
<link rel="alternate" type="application/json+oembed" href="http://127.0.0.1:82/wordpress/index.php?rest_route=%2Foembed%2F1.0%2Fembed&#038;url=http%3A%2F%2F127.0.0.1%3A82%2Fwordpress%2F" />
<link rel="alternate" type="text/xml+oembed" href="http://127.0.0.1:82/wordpress/index.php?rest_route=%2Foembed%2F1.0%2Fembed&#038;url=http%3A%2F%2F127.0.0.1%3A82%2Fwordpress%2F&#038;format=xml" />
<style>.bg{opacity: 0; transition: opacity 1s; -webkit-transition: opacity 1s;} .bg-loaded{opacity: 1;}</style><!--[if IE]><link rel="stylesheet" type="text/css" href="http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/css/ie-fallback.css"><script src="//cdnjs.cloudflare.com/ajax/libs/html5shiv/3.6.1/html5shiv.js"></script><script>var head = document.getElementsByTagName('head')[0],style = document.createElement('style');style.type = 'text/css';style.styleSheet.cssText = ':before,:after{content:none !important';head.appendChild(style);setTimeout(function(){head.removeChild(style);}, 0);</script><script src="http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/libs/ie-flexibility.js"></script><![endif]-->	<noscript><style>.woocommerce-product-gallery{ opacity: 1 !important; }</style></noscript>
	<style type="text/css" media="print">#wpadminbar { display:none; }</style>
	<style type="text/css" media="screen">
	html { margin-top: 32px !important; }
	* html body { margin-top: 32px !important; }
	@media screen and ( max-width: 782px ) {
		html { margin-top: 46px !important; }
		* html body { margin-top: 46px !important; }
	}
</style>
	<link rel="icon" href="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/cropped-Auction512-32x32.jpg" sizes="32x32" />
<link rel="icon" href="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/cropped-Auction512-192x192.jpg" sizes="192x192" />
<link rel="apple-touch-icon" href="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/cropped-Auction512-180x180.jpg" />
<meta name="msapplication-TileImage" content="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/cropped-Auction512-270x270.jpg" />
<style id="custom-css" type="text/css">:root {--primary-color: #002447;}.sticky-add-to-cart--active, #wrapper,#main,#main.dark{background-color: #ffffff}.header-main{height: 100px}#logo img{max-height: 100px}#logo{width:125px;}#logo a{max-width:250px;}.header-top{min-height: 36px}.transparent .header-main{height: 265px}.transparent #logo img{max-height: 265px}.has-transparent + .page-title:first-of-type,.has-transparent + #main > .page-title,.has-transparent + #main > div > .page-title,.has-transparent + #main .page-header-wrapper:first-of-type .page-title{padding-top: 295px;}.header.show-on-scroll,.stuck .header-main{height:70px!important}.stuck #logo img{max-height: 70px!important}.header-bg-color, .header-wrapper {background-color: rgba(255,255,255,0.9)}.header-bottom {background-color: #f1f1f1}.header-main .nav > li > a{line-height: 16px }@media (max-width: 549px) {.header-main{height: 70px}#logo img{max-height: 70px}}.main-menu-overlay{background-color: rgba(121,197,231,0.32)}.nav-dropdown-has-arrow.nav-dropdown-has-border li.has-dropdown:before{border-bottom-color: #79c5e7;}.nav .nav-dropdown{border-color: #79c5e7 }.nav-dropdown{font-size:100%}.header-top{background-color:#002447!important;}/* Color */.accordion-title.active, .has-icon-bg .icon .icon-inner,.logo a, .primary.is-underline, .primary.is-link, .badge-outline .badge-inner, .nav-outline > li.active> a,.nav-outline >li.active > a, .cart-icon strong,[data-color='primary'], .is-outline.primary{color: #002447;}/* Color !important */[data-text-color="primary"]{color: #002447!important;}/* Background Color */[data-text-bg="primary"]{background-color: #002447;}/* Background */.scroll-to-bullets a,.featured-title, .label-new.menu-item > a:after, .nav-pagination > li > .current,.nav-pagination > li > span:hover,.nav-pagination > li > a:hover,.has-hover:hover .badge-outline .badge-inner,button[type="submit"], .button.wc-forward:not(.checkout):not(.checkout-button), .button.submit-button, .button.primary:not(.is-outline),.featured-table .title,.is-outline:hover, .has-icon:hover .icon-label,.nav-dropdown-bold .nav-column li > a:hover, .nav-dropdown.nav-dropdown-bold > li > a:hover, .nav-dropdown-bold.dark .nav-column li > a:hover, .nav-dropdown.nav-dropdown-bold.dark > li > a:hover, .is-outline:hover, .tagcloud a:hover,.grid-tools a, input[type='submit']:not(.is-form), .box-badge:hover .box-text, input.button.alt,.nav-box > li > a:hover,.nav-box > li.active > a,.nav-pills > li.active > a ,.current-dropdown .cart-icon strong, .cart-icon:hover strong, .nav-line-bottom > li > a:before, .nav-line-grow > li > a:before, .nav-line > li > a:before,.banner, .header-top, .slider-nav-circle .flickity-prev-next-button:hover svg, .slider-nav-circle .flickity-prev-next-button:hover .arrow, .primary.is-outline:hover, .button.primary:not(.is-outline), input[type='submit'].primary, input[type='submit'].primary, input[type='reset'].button, input[type='button'].primary, .badge-inner{background-color: #002447;}/* Border */.nav-vertical.nav-tabs > li.active > a,.scroll-to-bullets a.active,.nav-pagination > li > .current,.nav-pagination > li > span:hover,.nav-pagination > li > a:hover,.has-hover:hover .badge-outline .badge-inner,.accordion-title.active,.featured-table,.is-outline:hover, .tagcloud a:hover,blockquote, .has-border, .cart-icon strong:after,.cart-icon strong,.blockUI:before, .processing:before,.loading-spin, .slider-nav-circle .flickity-prev-next-button:hover svg, .slider-nav-circle .flickity-prev-next-button:hover .arrow, .primary.is-outline:hover{border-color: #002447}.nav-tabs > li.active > a{border-top-color: #002447}.widget_shopping_cart_content .blockUI.blockOverlay:before { border-left-color: #002447 }.woocommerce-checkout-review-order .blockUI.blockOverlay:before { border-left-color: #002447 }/* Fill */.slider .flickity-prev-next-button:hover svg,.slider .flickity-prev-next-button:hover .arrow{fill: #002447;}/* Background Color */[data-icon-label]:after, .secondary.is-underline:hover,.secondary.is-outline:hover,.icon-label,.button.secondary:not(.is-outline),.button.alt:not(.is-outline), .badge-inner.on-sale, .button.checkout, .single_add_to_cart_button, .current .breadcrumb-step{ background-color:#79c5e7; }[data-text-bg="secondary"]{background-color: #79c5e7;}/* Color */.secondary.is-underline,.secondary.is-link, .secondary.is-outline,.stars a.active, .star-rating:before, .woocommerce-page .star-rating:before,.star-rating span:before, .color-secondary{color: #79c5e7}/* Color !important */[data-text-color="secondary"]{color: #79c5e7!important;}/* Border */.secondary.is-outline:hover{border-color:#79c5e7}.success.is-underline:hover,.success.is-outline:hover,.success{background-color: #87f41a}.success-color, .success.is-link, .success.is-outline{color: #87f41a;}.success-border{border-color: #87f41a!important;}/* Color !important */[data-text-color="success"]{color: #87f41a!important;}/* Background Color */[data-text-bg="success"]{background-color: #87f41a;}.alert.is-underline:hover,.alert.is-outline:hover,.alert{background-color: #d60404}.alert.is-link, .alert.is-outline, .color-alert{color: #d60404;}/* Color !important */[data-text-color="alert"]{color: #d60404!important;}/* Background Color */[data-text-bg="alert"]{background-color: #d60404;}body{font-family:"Tajawal", sans-serif}body{font-weight: 0}.nav > li > a {font-family:"Tajawal", sans-serif;}.mobile-sidebar-levels-2 .nav > li > ul > li > a {font-family:"Tajawal", sans-serif;}.nav > li > a {font-weight: 700;}.mobile-sidebar-levels-2 .nav > li > ul > li > a {font-weight: 700;}h1,h2,h3,h4,h5,h6,.heading-font, .off-canvas-center .nav-sidebar.nav-vertical > li > a{font-family: "Tajawal", sans-serif;}h1,h2,h3,h4,h5,h6,.heading-font,.banner h1,.banner h2{font-weight: 700;}.alt-font{font-family: "Cairo", sans-serif;}.alt-font{font-weight: 0!important;}.header:not(.transparent) .top-bar-nav > li > a {color: #ffffff;}.header:not(.transparent) .top-bar-nav.nav > li > a:hover,.header:not(.transparent) .top-bar-nav.nav > li.active > a,.header:not(.transparent) .top-bar-nav.nav > li.current > a,.header:not(.transparent) .top-bar-nav.nav > li > a.active,.header:not(.transparent) .top-bar-nav.nav > li > a.current{color: #f2dcc5;}.top-bar-nav.nav-line-bottom > li > a:before,.top-bar-nav.nav-line-grow > li > a:before,.top-bar-nav.nav-line > li > a:before,.top-bar-nav.nav-box > li > a:hover,.top-bar-nav.nav-box > li.active > a,.top-bar-nav.nav-pills > li > a:hover,.top-bar-nav.nav-pills > li.active > a{color:#FFF!important;background-color: #f2dcc5;}.header:not(.transparent) .header-nav-main.nav > li > a {color: #79c5e7;}.header:not(.transparent) .header-nav-main.nav > li > a:hover,.header:not(.transparent) .header-nav-main.nav > li.active > a,.header:not(.transparent) .header-nav-main.nav > li.current > a,.header:not(.transparent) .header-nav-main.nav > li > a.active,.header:not(.transparent) .header-nav-main.nav > li > a.current{color: #002447;}.header-nav-main.nav-line-bottom > li > a:before,.header-nav-main.nav-line-grow > li > a:before,.header-nav-main.nav-line > li > a:before,.header-nav-main.nav-box > li > a:hover,.header-nav-main.nav-box > li.active > a,.header-nav-main.nav-pills > li > a:hover,.header-nav-main.nav-pills > li.active > a{color:#FFF!important;background-color: #002447;}a{color: #79c5e7;}a:hover{color: #002447;}.tagcloud a:hover{border-color: #002447;background-color: #002447;}.widget a{color: #79c5e7;}.widget a:hover{color: #002447;}.widget .tagcloud a:hover{border-color: #002447; background-color: #002447;}.has-equal-box-heights .box-image {padding-top: 100%;}@media screen and (min-width: 550px){.products .box-vertical .box-image{min-width: 247px!important;width: 247px!important;}}.header-main .social-icons,.header-main .cart-icon strong,.header-main .menu-title,.header-main .header-button > .button.is-outline,.header-main .nav > li > a > i:not(.icon-angle-down){color: #79c5e7!important;}.header-main .header-button > .button.is-outline,.header-main .cart-icon strong:after,.header-main .cart-icon strong{border-color: #79c5e7!important;}.header-main .header-button > .button:not(.is-outline){background-color: #79c5e7!important;}.header-main .current-dropdown .cart-icon strong,.header-main .header-button > .button:hover,.header-main .header-button > .button:hover i,.header-main .header-button > .button:hover span{color:#FFF!important;}.header-main .menu-title:hover,.header-main .social-icons a:hover,.header-main .header-button > .button.is-outline:hover,.header-main .nav > li > a:hover > i:not(.icon-angle-down){color: #002447!important;}.header-main .current-dropdown .cart-icon strong,.header-main .header-button > .button:hover{background-color: #002447!important;}.header-main .current-dropdown .cart-icon strong:after,.header-main .current-dropdown .cart-icon strong,.header-main .header-button > .button:hover{border-color: #002447!important;}.footer-1{background-color: #ffffff}.footer-2{background-color: #79c5e7}.absolute-footer, html{background-color: #002447}@media (max-width: 849px){#wpadminbar{display: none!important;}html{margin-top: 0!important}}@media (min-width: 850px){.mfp-content,.stuck,button.mfp-close{top: 32px!important;}.is-full-height{height: calc(100vh - 32px)!important;}}.xdebug-var-dump{z-index: 999999;}.shortcode-error{border: 2px dashed #000;padding: 20px;color:#fff;font-size:16px;background-color: #71cedf;}.custom-product-page .shortcode-error {padding: 15% 10%;text-align: center;}.edit-block-wrapper{position: relative;}.edit-block-button{font-size: 12px!important;background-color: #555!important;margin: 6px 2px 3px 0px!important;border-radius: 4px!important;}.edit-block-button-builder{background-color: #00a0d2!important;}.label-new.menu-item > a:after{content:"New";}.label-hot.menu-item > a:after{content:"Hot";}.label-sale.menu-item > a:after{content:"Sale";}.label-popular.menu-item > a:after{content:"Popular";}</style></head>

<body class="home page-template page-template-page-blank page-template-page-blank-php page page-id-696 page-child parent-pageid-689 logged-in admin-bar no-customize-support wp-custom-logo theme-flatsome woocommerce-no-js header-shadow lightbox nav-dropdown-has-arrow nav-dropdown-has-shadow nav-dropdown-has-border parallax-mobile">

	<script type="text/javascript">
		(function() {
			var request, b = document.body, c = 'className', cs = 'customize-support', rcs = new RegExp('(^|\\s+)(no-)?'+cs+'(\\s+|$)');

				request = true;
	
			b[c] = b[c].replace( rcs, ' ' );
			// The customizer requires postMessage and CORS (if the site is cross domain).
			b[c] += ( window.postMessage && request ? ' ' : ' no-' ) + cs;
		}());
	</script>
			<div id="wpadminbar" class="nojq nojs">
						<div class="quicklinks" id="wp-toolbar" role="navigation" aria-label="Toolbar">
				<ul id='wp-admin-bar-root-default' class="ab-top-menu"><li id='wp-admin-bar-wp-logo' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/about.php'><span class="ab-icon"></span><span class="screen-reader-text">About WordPress</span></a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-wp-logo-default' class="ab-submenu"><li id='wp-admin-bar-about'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/about.php'>About WordPress</a></li></ul><ul id='wp-admin-bar-wp-logo-external' class="ab-sub-secondary ab-submenu"><li id='wp-admin-bar-wporg'><a class='ab-item' href='https://wordpress.org/'>WordPress.org</a></li><li id='wp-admin-bar-documentation'><a class='ab-item' href='https://wordpress.org/support/'>Documentation</a></li><li id='wp-admin-bar-support-forums'><a class='ab-item' href='https://wordpress.org/support/forums/'>Support</a></li><li id='wp-admin-bar-feedback'><a class='ab-item' href='https://wordpress.org/support/forum/requests-and-feedback'>Feedback</a></li></ul></div></li><li id='wp-admin-bar-site-name' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/'>admim&#039;s Blog!</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-site-name-default' class="ab-submenu"><li id='wp-admin-bar-dashboard'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/'>Dashboard</a></li></ul><ul id='wp-admin-bar-appearance' class="ab-submenu"><li id='wp-admin-bar-themes'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/themes.php'>Themes</a></li><li id='wp-admin-bar-widgets'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/widgets.php'>Widgets</a></li><li id='wp-admin-bar-menus'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/nav-menus.php'>Menus</a></li></ul></div></li><li id='wp-admin-bar-flatsome_panel' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=flatsome-panel'><svg style="width:20px; margin-top:-4px; height:20px;vertical-align:middle;" width="184px" height="186px" viewBox="0 0 184 186" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"> <!-- Generator: Sketch 3.8.1 (29687) - http://www.bohemiancoding.com/sketch --> <title>Logo-white</title> <desc>Created with Sketch.</desc> <defs></defs> <g id="Logo" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"> <g id="Logo-white" fill="#FFFFFF"> <g id="Group"> <path d="M92.6963305,153.35517 L69.6726254,130.331465 L92.6963305,107.30776 L92.6963305,66.7055226 L49.3715069,110.030346 L32.472925,93.1317642 L92.6963305,32.9083587 L92.6963305,0.803652143 L0.106126393,93.3938562 L92.6963305,185.98406 L92.6963305,153.35517 Z" id="Combined-Shape"></path> </g> <g id="Group" opacity="0.502623601" transform="translate(136.800003, 93.000000) scale(-1, 1) translate(-136.800003, -93.000000) translate(90.300003, 0.000000)"> <path d="M92.6963305,153.35517 L69.6726254,130.331465 L92.6963305,107.30776 L92.6963305,66.7055226 L49.3715069,110.030346 L32.472925,93.1317642 L92.6963305,32.9083587 L92.6963305,0.803652143 L0.106126393,93.3938562 L92.6963305,185.98406 L92.6963305,153.35517 Z" opacity="0.387068563"></path> </g> </g> </g> </svg> Flatsome</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-flatsome_panel-default' class="ab-submenu"><li id='wp-admin-bar-theme_options' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D='><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-admin-generic" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Theme Options</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-theme_options-default' class="ab-submenu"><li id='wp-admin-bar-options_header' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=header'><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-arrow-up-alt dashicons-header" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Header</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_header-default' class="ab-submenu"><li id='wp-admin-bar-options_header_presets'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=header-presets'>Presets</a></li><li id='wp-admin-bar-options_header_logo'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=title_tagline'>Logo & Site Identity</a></li><li id='wp-admin-bar-options_header_top'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=top_bar'>Top Bar</a></li><li id='wp-admin-bar-options_header_main'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=main_bar'>Header Main</a></li><li id='wp-admin-bar-options_header_bottom'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=bottom_bar'> Header Bottom</a></li><li id='wp-admin-bar-options_header_mobile'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=header_mobile'> Header Mobile</a></li><li id='wp-admin-bar-options_header_sticky'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=header_sticky'> Sticky Header</a></li><li id='wp-admin-bar-options_header_dropdown'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=header_dropdown'>Dropdown Style</a></li></ul></div></li><li id='wp-admin-bar-options_layout'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=layout'><span class="dashicons dashicons-editor-table" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Layout</a></li><li id='wp-admin-bar-options_static_front_page'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=static_front_page'><span class="dashicons dashicons-admin-home" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Homepage</a></li><li id='wp-admin-bar-options_style' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=style'><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-admin-appearance" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Style</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_style-default' class="ab-submenu"><li id='wp-admin-bar-options_style_colors'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=colors'>Colors</a></li><li id='wp-admin-bar-options_style_global'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=global-styles'>Global Styles</a></li><li id='wp-admin-bar-options_style_type'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=type'>Typography</a></li><li id='wp-admin-bar-options_style_css'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=custom-css'>Custom CSS</a></li><li id='wp-admin-bar-options_style_lightbox'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=lightbox'>Image Lightbox</a></li></ul></div></li><li id='wp-admin-bar-options_shop' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=woocommerce'><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-cart" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span>&nbsp;WooCommerce</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_shop-default' class="ab-submenu"><li id='wp-admin-bar-options_shop_store_notice'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=woocommerce_store_notice'>Store Notice</a></li><li id='wp-admin-bar-options_shop_category_page'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=woocommerce_product_catalog'>Product Catalog</a></li><li id='wp-admin-bar-options_shop_product_page'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=product-page'>Product Page</a></li><li id='wp-admin-bar-options_shop_my_account'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=fl-my-account'>My Account</a></li><li id='wp-admin-bar-options_shop_payment_icons'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=payment-icons'>Payment Icons</a></li><li id='wp-admin-bar-options_shop_product_images'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=woocommerce_product_images'>Product Images</a></li><li id='wp-admin-bar-options_shop_checkout'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=woocommerce_checkout'>Checkout</a></li><li id='wp-admin-bar-options_shop_cart'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=cart-checkout'>Cart</a></li><li id='wp-admin-bar-options_advanced_woocommerce_2'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-woocommerce'>Advanced</a></li></ul></div></li><li id='wp-admin-bar-options_pages'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=pages'><span class="dashicons dashicons-admin-page" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Pages</a></li><li id='wp-admin-bar-options_blog'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=blog'><span class="dashicons dashicons-edit" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Blog</a></li><li id='wp-admin-bar-options_portfolio'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=fl-portfolio'><span class="dashicons dashicons-portfolio" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Portfolio</a></li><li id='wp-admin-bar-options_footer'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=footer'><span class="dashicons dashicons-arrow-down-alt" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Footer</a></li><li id='wp-admin-bar-options_menus' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=nav_menus'><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-menu " style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Menus</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_menus-default' class="ab-submenu"><li id='wp-admin-bar-options_menus_backend'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/nav-menus.php'>Back-end editor</a></li></ul></div></li><li id='wp-admin-bar-options_widgets' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bpanel%5D=widgets'><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-welcome-widgets-menus" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Widgets</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_widgets-default' class="ab-submenu"><li id='wp-admin-bar-options_widgets_backend'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/widgets.php'>Back-end editor</a></li></ul></div></li><li id='wp-admin-bar-options_share'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=share'><span class="dashicons dashicons-share" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Share</a></li><li id='wp-admin-bar-options_notifications'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=notifications'><span class="dashicons dashicons-testimonial" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Notifications</a></li><li id='wp-admin-bar-options_reset'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http://127.0.0.1:82/wordpress/&#038;autofocus%5Bsection%5D=advanced'><span class="dashicons dashicons-admin-generic" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Reset</a></li></ul></div></li><li id='wp-admin-bar-options_advanced' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab='><span class="wp-admin-bar-arrow" aria-hidden="true"></span><span class="dashicons dashicons-admin-tools" style="font: normal 20px/1 'dashicons';-webkit-font-smoothing: antialiased;padding-right: 4px;margin-top:3px;"></span> Advanced</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-options_advanced-default' class="ab-submenu"><li id='wp-admin-bar-options_advanced_custom_scripts'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-globalsettings'>Global Settings</a></li><li id='wp-admin-bar-options_advanced_custom_css'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-customcss'>Custom CSS</a></li><li id='wp-admin-bar-options_advanced_performance'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-performance'>Performance</a></li><li id='wp-admin-bar-options_advanced_site_loader'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-siteloader'>Site Loader</a></li><li id='wp-admin-bar-options_advanced_site_search'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-sitesearch'>Site Search</a></li><li id='wp-admin-bar-options_advanced_instagram_api'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-instagram'>Instagram</a></li><li id='wp-admin-bar-options_advanced_google_apis'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-googleapis'>Google APIs</a></li><li id='wp-admin-bar-options_advanced_maintenance'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-maintenancemode'>Maintenance</a></li><li id='wp-admin-bar-options_advanced_404'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-404page'>404 Page</a></li><li id='wp-admin-bar-options_advanced_woocommerce'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-woocommerce'>WooCommerce</a></li><li id='wp-admin-bar-options_advanced_catalog_mode'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-catalogmode'>Catalog Mode</a></li><li id='wp-admin-bar-options_advanced_infinite_scroll'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-infinitescroll'>Infinite Scroll</a></li><li id='wp-admin-bar-options_advanced_portfolio'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-portfolio'>Portfolio</a></li><li id='wp-admin-bar-options_advanced_mobile'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-mobile'>Mobile</a></li><li id='wp-admin-bar-options_advanced_integrations'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-integrations'>Integrations</a></li><li id='wp-admin-bar-options_advanced_backup'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=optionsframework&#038;tab=of-option-backupandimport'>Backup / Import</a></li></ul></div></li><li id='wp-admin-bar-flatsome_panel_license'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=flatsome-panel'>Theme Registration</a></li><li id='wp-admin-bar-flatsome_panel_support'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=flatsome-panel-support'>Help & Guides</a></li><li id='wp-admin-bar-flatsome_panel_changelog'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=flatsome-panel-changelog'>Change log</a></li><li id='wp-admin-bar-flatsome_panel_setup_wizard'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=flatsome-setup'>Setup Wizard</a></li></ul></div></li><li id='wp-admin-bar-customize' class="hide-if-no-customize"><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/customize.php?url=http%3A%2F%2F127.0.0.1%3A82%2Fwordpress%2F'>Customize</a></li><li id='wp-admin-bar-comments'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/edit-comments.php'><span class="ab-icon"></span><span class="ab-label awaiting-mod pending-count count-0" aria-hidden="true">0</span><span class="screen-reader-text comments-in-moderation-text">0 Comments in moderation</span></a></li><li id='wp-admin-bar-new-content' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php'><span class="ab-icon"></span><span class="ab-label">New</span></a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-new-content-default' class="ab-submenu"><li id='wp-admin-bar-new-post'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php'>Post</a></li><li id='wp-admin-bar-new-media'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/media-new.php'>Media</a></li><li id='wp-admin-bar-new-page'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=page'>Page</a></li><li id='wp-admin-bar-new-blocks'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=blocks'>Block</a></li><li id='wp-admin-bar-new-product'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=product'>Product</a></li><li id='wp-admin-bar-new-shop_order'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=shop_order'>Order</a></li><li id='wp-admin-bar-new-shop_coupon'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=shop_coupon'>Coupon</a></li><li id='wp-admin-bar-new-3d-flip-book'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=3d-flip-book'>3D FlipBook</a></li><li id='wp-admin-bar-new-featured_item'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post-new.php?post_type=featured_item'>Portfolio</a></li><li id='wp-admin-bar-new-user'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/user-new.php'>User</a></li><li id='wp-admin-bar-members-new-role'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/admin.php?page=members'>Role</a></li></ul></div></li><li id='wp-admin-bar-edit' class="menupop"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/post.php?post=696&#038;action=edit'>Edit Page</a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-edit-default' class="ab-submenu"><li id='wp-admin-bar-edit_uxbuilder'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/post.php?post=696&#038;action=edit&#038;app=uxbuilder&#038;type=editor'>Edit with UX Builder</a></li></ul></div></li></ul><ul id='wp-admin-bar-top-secondary' class="ab-top-secondary ab-top-menu"><li id='wp-admin-bar-search' class="admin-bar-search"><div class="ab-item ab-empty-item" tabindex="-1"><form action="http://127.0.0.1:82/wordpress/" method="get" id="adminbarsearch"><input class="adminbar-input" name="s" id="adminbar-search" type="text" value="" maxlength="150" /><label for="adminbar-search" class="screen-reader-text">Search</label><input type="submit" class="adminbar-button" value="Search"/></form></div></li><li id='wp-admin-bar-my-account' class="menupop with-avatar"><a class='ab-item' aria-haspopup="true" href='http://127.0.0.1:82/wordpress/wp-admin/profile.php'>Howdy, <span class="display-name">amjad altnbour</span><img alt='' src='http://0.gravatar.com/avatar/06e87b19b188fff31c165aa0cee3a4c0?s=26&#038;d=mm&#038;r=g' srcset='http://0.gravatar.com/avatar/06e87b19b188fff31c165aa0cee3a4c0?s=52&#038;d=mm&#038;r=g 2x' class='avatar avatar-26 photo' height='26' width='26' loading='lazy'/></a><div class="ab-sub-wrapper"><ul id='wp-admin-bar-user-actions' class="ab-submenu"><li id='wp-admin-bar-user-info'><a class='ab-item' tabindex="-1" href='http://127.0.0.1:82/wordpress/wp-admin/profile.php'><img alt='' src='http://0.gravatar.com/avatar/06e87b19b188fff31c165aa0cee3a4c0?s=64&#038;d=mm&#038;r=g' srcset='http://0.gravatar.com/avatar/06e87b19b188fff31c165aa0cee3a4c0?s=128&#038;d=mm&#038;r=g 2x' class='avatar avatar-64 photo' height='64' width='64' loading='lazy'/><span class='display-name'>amjad altnbour</span><span class='username'>admim</span></a></li><li id='wp-admin-bar-edit-profile'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-admin/profile.php'>Edit Profile</a></li><li id='wp-admin-bar-logout'><a class='ab-item' href='http://127.0.0.1:82/wordpress/wp-login.php?action=logout&#038;_wpnonce=eee2e548bf'>Log Out</a></li></ul></div></li></ul>			</div>
						<a class="screen-reader-shortcut" href="http://127.0.0.1:82/wordpress/wp-login.php?action=logout&#038;_wpnonce=eee2e548bf">Log Out</a>
					</div>

		
<a class="skip-link screen-reader-text" href="#main">Skip to content</a>

<div id="wrapper">

	<div class="page-loader fixed fill z-top-3 ">
	<div class="page-loader-inner x50 y50 md-y50 md-x50 lg-y50 lg-x50 absolute">
		<div class="page-loader-logo" style="padding-bottom: 30px;">
	    	<!-- Header logo -->
<a href="http://127.0.0.1:82/wordpress/" title="admim&#039;s Blog! - Just another WordPress site" rel="home">
    <img width="125" height="100" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Auction.jpg" class="header_logo header-logo" alt="admim&#039;s Blog!"/><img  width="125" height="100" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Auction512.jpg" class="header-logo-dark" alt="admim&#039;s Blog!"/></a>
	    </div>
		<div class="page-loader-spin"><div class="loading-spin"></div></div>
	</div>
	<style>
		.page-loader{opacity: 0; transition: opacity .3s; transition-delay: .3s;
			background-color: #fff;
		}
		.loading-site .page-loader{opacity: .98;}
		.page-loader-logo{max-width: px; animation: pageLoadZoom 1.3s ease-out; -webkit-animation: pageLoadZoom 1.3s ease-out;}
		.page-loader-spin{animation: pageLoadZoomSpin 1.3s ease-out;}
		.page-loader-spin .loading-spin{width: 40px; height: 40px; }
		@keyframes pageLoadZoom {
		    0%   {opacity:0; transform: translateY(30px);}
		    100% {opacity:1; transform: translateY(0);}
		}
		@keyframes pageLoadZoomSpin {
		    0%   {opacity:0; transform: translateY(60px);}
		    100% {opacity:1; transform: translateY(0);}
		}
	</style>
</div>

	<header id="header" class="header header-full-width has-sticky sticky-jump">
		<div class="header-wrapper">
			<div id="top-bar" class="header-top hide-for-sticky nav-dark">
    <div class="flex-row container">
      <div class="flex-col hide-for-medium flex-left">
          <ul class="nav nav-left medium-nav-center nav-small  nav-divided">
              <li class="html custom html_topbar_left"><strong class="uppercase">Welcome to amjad books store</strong></li>          </ul>
      </div>

      <div class="flex-col hide-for-medium flex-center">
          <ul class="nav nav-center nav-small  nav-divided">
                        </ul>
      </div>

      <div class="flex-col hide-for-medium flex-right">
         <ul class="nav top-bar-nav nav-right nav-small  nav-divided">
              <li class="has-dropdown header-language-dropdown">
	<a href="#">
		Languages				<i class="icon-angle-down" ></i>	</a>
	<ul class="nav-dropdown nav-dropdown-default">
		<li><a>You need Polylang or WPML plugin for this to work. You can remove it from Theme Options.</a></li>	</ul>
</li>
<li class="header-divider"></li><li class="html header-social-icons ml-0">
	<div class="social-icons follow-icons" ><a href="https://www.facebook.com/amjadbooksdp" target="_blank" data-label="Facebook"  rel="noopener noreferrer nofollow" class="icon plain facebook tooltip" title="Follow on Facebook"><i class="icon-facebook" ></i></a><a href="https://twitter.com/daramjadbooks" target="_blank"  data-label="Twitter"  rel="noopener noreferrer nofollow" class="icon plain  twitter tooltip" title="Follow on Twitter"><i class="icon-twitter" ></i></a><a href="mailto:your@email" data-label="E-mail"  rel="nofollow" class="icon plain  email tooltip" title="Send us an email"><i class="icon-envelop" ></i></a></div></li>          </ul>
      </div>

            <div class="flex-col show-for-medium flex-grow">
          <ul class="nav nav-center nav-small mobile-nav  nav-divided">
              <li class="html custom html_topbar_left"><strong class="uppercase">Welcome to amjad books store</strong></li><li class="has-dropdown header-language-dropdown">
	<a href="#">
		Languages				<i class="icon-angle-down" ></i>	</a>
	<ul class="nav-dropdown nav-dropdown-default">
		<li><a>You need Polylang or WPML plugin for this to work. You can remove it from Theme Options.</a></li>	</ul>
</li>
          </ul>
      </div>
      
    </div>
</div>
<div id="masthead" class="header-main ">
      <div class="header-inner flex-row container logo-left medium-logo-center" role="navigation">

          <!-- Logo -->
          <div id="logo" class="flex-col logo">
            <!-- Header logo -->
<a href="http://127.0.0.1:82/wordpress/" title="admim&#039;s Blog! - Just another WordPress site" rel="home">
    <img width="125" height="100" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Auction.jpg" class="header_logo header-logo" alt="admim&#039;s Blog!"/><img  width="125" height="100" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Auction512.jpg" class="header-logo-dark" alt="admim&#039;s Blog!"/></a>
          </div>

          <!-- Mobile Left Elements -->
          <div class="flex-col show-for-medium flex-left">
            <ul class="mobile-nav nav nav-left ">
              <li class="nav-icon has-icon">
  <div class="header-button">		<a href="#" data-open="#main-menu" data-pos="left" data-bg="main-menu-overlay" data-color="" class="icon primary button circle is-small" aria-label="Menu" aria-controls="main-menu" aria-expanded="false">
		
		  <i class="icon-menu" ></i>
		  		</a>
	 </div> </li>            </ul>
          </div>

          <!-- Left Elements -->
          <div class="flex-col hide-for-medium flex-left
            flex-grow">
            <ul class="header-nav header-nav-main nav nav-left  nav-uppercase" >
              <li class="header-search header-search-dropdown has-icon has-dropdown menu-item-has-children">
	<div class="header-button">	<a href="#" aria-label="Search" class="icon primary button circle is-small"><i class="icon-search" ></i></a>
	</div>	<ul class="nav-dropdown nav-dropdown-default">
	 	<li class="header-search-form search-form html relative has-icon">
	<div class="header-search-form-wrapper">
		<div class="searchform-wrapper ux-search-box relative is-normal"><form role="search" method="get" class="searchform" action="http://127.0.0.1:82/wordpress/">
	<div class="flex-row relative">
						<div class="flex-col flex-grow">
			<label class="screen-reader-text" for="woocommerce-product-search-field-0">Search for:</label>
			<input type="search" id="woocommerce-product-search-field-0" class="search-field mb-0" placeholder="Search&hellip;" value="" name="s" />
			<input type="hidden" name="post_type" value="product" />
					</div>
		<div class="flex-col">
			<button type="submit" value="Search" class="ux-search-submit submit-button secondary button icon mb-0" aria-label="Submit">
				<i class="icon-search" ></i>			</button>
		</div>
	</div>
	<div class="live-search-results text-left z-top"></div>
</form>
</div>	</div>
</li>	</ul>
</li>
            </ul>
          </div>

          <!-- Right Elements -->
          <div class="flex-col hide-for-medium flex-right">
            <ul class="header-nav header-nav-main nav nav-right  nav-uppercase">
              <li class="account-item has-icon
     has-dropdown"
>

<a href="" class="account-link account-login
  "
  title="My account">

			<span class="header-account-title">
		amjad altnbour		</span>
	
  
</a>



<ul class="nav-dropdown  nav-dropdown-default">
    
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--dashboard is-active active">
          <a href="http://127.0.0.1:82/wordpress">Dashboard</a>
      <!-- empty -->
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--orders">
          <a href="http://127.0.0.1:82/wordpress?orders">Orders</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--downloads">
          <a href="http://127.0.0.1:82/wordpress?downloads">Downloads</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--edit-address">
          <a href="http://127.0.0.1:82/wordpress?edit-address">Addresses</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--edit-account">
          <a href="http://127.0.0.1:82/wordpress?edit-account">Account details</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction-setting">
          <a href="http://127.0.0.1:82/wordpress?my-auction-setting">Auctions Setting</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction">
          <a href="http://127.0.0.1:82/wordpress?my-auction">My Auctions</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction-watchlist">
          <a href="http://127.0.0.1:82/wordpress?my-auction-watchlist">My Auctions Watchlist</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--customer-logout">
          <a href="http://127.0.0.1:82/wordpress?customer-logout"></a>
        </li>
    		<li class="wishlist-account-element ">
			<a href="/wordpress/?wishlist-action"></a>
		</li>
		  <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--customer-logout">
    <a href="http://127.0.0.1:82/wordpress?customer-logout">Logout</a>
  </li>
</ul>

</li>
<li class="header-divider"></li><li class="cart-item has-icon has-dropdown">

<a href="http://127.0.0.1:82/wordpress/?page_id=683" title="Cart" class="header-cart-link is-small">


<span class="header-cart-title">
   Cart   /      <span class="cart-price"><span class="woocommerce-Price-amount amount"><bdi><span class="woocommerce-Price-currencySymbol">&#x62f;.&#x627;</span>0.00</bdi></span></span>
  </span>

    <span class="cart-icon image-icon">
    <strong>0</strong>
  </span>
  </a>

 <ul class="nav-dropdown nav-dropdown-default">
    <li class="html widget_shopping_cart">
      <div class="widget_shopping_cart_content">
        

	<p class="woocommerce-mini-cart__empty-message">No products in the cart.</p>


      </div>
    </li>
     </ul>

</li>
            </ul>
          </div>

          <!-- Mobile Right Elements -->
          <div class="flex-col show-for-medium flex-right">
            <ul class="mobile-nav nav nav-right ">
              <li class="cart-item has-icon">

      <a href="http://127.0.0.1:82/wordpress/?page_id=683" class="header-cart-link off-canvas-toggle nav-top-link is-small" data-open="#cart-popup" data-class="off-canvas-cart" title="Cart" data-pos="right">
  
    <span class="cart-icon image-icon">
    <strong>0</strong>
  </span>
  </a>


  <!-- Cart Sidebar Popup -->
  <div id="cart-popup" class="mfp-hide widget_shopping_cart">
  <div class="cart-popup-inner inner-padding">
      <div class="cart-popup-title text-center">
          <h4 class="uppercase">Cart</h4>
          <div class="is-divider"></div>
      </div>
      <div class="widget_shopping_cart_content">
          

	<p class="woocommerce-mini-cart__empty-message">No products in the cart.</p>


      </div>
             <div class="cart-sidebar-content relative"></div><div class="payment-icons inline-block"><div class="payment-icon"><svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 64 32">
<path d="M35.255 12.078h-2.396c-0.229 0-0.444 0.114-0.572 0.303l-3.306 4.868-1.4-4.678c-0.088-0.292-0.358-0.493-0.663-0.493h-2.355c-0.284 0-0.485 0.28-0.393 0.548l2.638 7.745-2.481 3.501c-0.195 0.275 0.002 0.655 0.339 0.655h2.394c0.227 0 0.439-0.111 0.569-0.297l7.968-11.501c0.191-0.275-0.006-0.652-0.341-0.652zM19.237 16.718c-0.23 1.362-1.311 2.276-2.691 2.276-0.691 0-1.245-0.223-1.601-0.644-0.353-0.417-0.485-1.012-0.374-1.674 0.214-1.35 1.313-2.294 2.671-2.294 0.677 0 1.227 0.225 1.589 0.65 0.365 0.428 0.509 1.027 0.404 1.686zM22.559 12.078h-2.384c-0.204 0-0.378 0.148-0.41 0.351l-0.104 0.666-0.166-0.241c-0.517-0.749-1.667-1-2.817-1-2.634 0-4.883 1.996-5.321 4.796-0.228 1.396 0.095 2.731 0.888 3.662 0.727 0.856 1.765 1.212 3.002 1.212 2.123 0 3.3-1.363 3.3-1.363l-0.106 0.662c-0.040 0.252 0.155 0.479 0.41 0.479h2.147c0.341 0 0.63-0.247 0.684-0.584l1.289-8.161c0.040-0.251-0.155-0.479-0.41-0.479zM8.254 12.135c-0.272 1.787-1.636 1.787-2.957 1.787h-0.751l0.527-3.336c0.031-0.202 0.205-0.35 0.41-0.35h0.345c0.899 0 1.747 0 2.185 0.511 0.262 0.307 0.341 0.761 0.242 1.388zM7.68 7.473h-4.979c-0.341 0-0.63 0.248-0.684 0.584l-2.013 12.765c-0.040 0.252 0.155 0.479 0.41 0.479h2.378c0.34 0 0.63-0.248 0.683-0.584l0.543-3.444c0.053-0.337 0.343-0.584 0.683-0.584h1.575c3.279 0 5.172-1.587 5.666-4.732 0.223-1.375 0.009-2.456-0.635-3.212-0.707-0.832-1.962-1.272-3.628-1.272zM60.876 7.823l-2.043 12.998c-0.040 0.252 0.155 0.479 0.41 0.479h2.055c0.34 0 0.63-0.248 0.683-0.584l2.015-12.765c0.040-0.252-0.155-0.479-0.41-0.479h-2.299c-0.205 0.001-0.379 0.148-0.41 0.351zM54.744 16.718c-0.23 1.362-1.311 2.276-2.691 2.276-0.691 0-1.245-0.223-1.601-0.644-0.353-0.417-0.485-1.012-0.374-1.674 0.214-1.35 1.313-2.294 2.671-2.294 0.677 0 1.227 0.225 1.589 0.65 0.365 0.428 0.509 1.027 0.404 1.686zM58.066 12.078h-2.384c-0.204 0-0.378 0.148-0.41 0.351l-0.104 0.666-0.167-0.241c-0.516-0.749-1.667-1-2.816-1-2.634 0-4.883 1.996-5.321 4.796-0.228 1.396 0.095 2.731 0.888 3.662 0.727 0.856 1.765 1.212 3.002 1.212 2.123 0 3.3-1.363 3.3-1.363l-0.106 0.662c-0.040 0.252 0.155 0.479 0.41 0.479h2.147c0.341 0 0.63-0.247 0.684-0.584l1.289-8.161c0.040-0.252-0.156-0.479-0.41-0.479zM43.761 12.135c-0.272 1.787-1.636 1.787-2.957 1.787h-0.751l0.527-3.336c0.031-0.202 0.205-0.35 0.41-0.35h0.345c0.899 0 1.747 0 2.185 0.511 0.261 0.307 0.34 0.761 0.241 1.388zM43.187 7.473h-4.979c-0.341 0-0.63 0.248-0.684 0.584l-2.013 12.765c-0.040 0.252 0.156 0.479 0.41 0.479h2.554c0.238 0 0.441-0.173 0.478-0.408l0.572-3.619c0.053-0.337 0.343-0.584 0.683-0.584h1.575c3.279 0 5.172-1.587 5.666-4.732 0.223-1.375 0.009-2.456-0.635-3.212-0.707-0.832-1.962-1.272-3.627-1.272z"></path>
</svg>
</div><div class="payment-icon"><svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 64 32">
<path d="M13.043 8.356c-0.46 0-0.873 0.138-1.24 0.413s-0.662 0.681-0.885 1.217c-0.223 0.536-0.334 1.112-0.334 1.727 0 0.568 0.119 0.99 0.358 1.265s0.619 0.413 1.141 0.413c0.508 0 1.096-0.131 1.765-0.393v1.327c-0.693 0.262-1.389 0.393-2.089 0.393-0.884 0-1.572-0.254-2.063-0.763s-0.736-1.229-0.736-2.161c0-0.892 0.181-1.712 0.543-2.462s0.846-1.32 1.452-1.709 1.302-0.584 2.089-0.584c0.435 0 0.822 0.038 1.159 0.115s0.7 0.217 1.086 0.421l-0.616 1.276c-0.369-0.201-0.673-0.333-0.914-0.398s-0.478-0.097-0.715-0.097zM19.524 12.842h-2.47l-0.898 1.776h-1.671l3.999-7.491h1.948l0.767 7.491h-1.551l-0.125-1.776zM19.446 11.515l-0.136-1.786c-0.035-0.445-0.052-0.876-0.052-1.291v-0.184c-0.153 0.408-0.343 0.84-0.569 1.296l-0.982 1.965h1.739zM27.049 12.413c0 0.711-0.257 1.273-0.773 1.686s-1.213 0.62-2.094 0.62c-0.769 0-1.389-0.153-1.859-0.46v-1.398c0.672 0.367 1.295 0.551 1.869 0.551 0.39 0 0.694-0.072 0.914-0.217s0.329-0.343 0.329-0.595c0-0.147-0.024-0.275-0.070-0.385s-0.114-0.214-0.201-0.309c-0.087-0.095-0.303-0.269-0.648-0.52-0.481-0.337-0.818-0.67-1.013-1s-0.293-0.685-0.293-1.066c0-0.439 0.108-0.831 0.324-1.176s0.523-0.614 0.922-0.806 0.857-0.288 1.376-0.288c0.755 0 1.446 0.168 2.073 0.505l-0.569 1.189c-0.543-0.252-1.044-0.378-1.504-0.378-0.289 0-0.525 0.077-0.71 0.23s-0.276 0.355-0.276 0.607c0 0.207 0.058 0.389 0.172 0.543s0.372 0.36 0.773 0.615c0.421 0.272 0.736 0.572 0.945 0.9s0.313 0.712 0.313 1.151zM33.969 14.618h-1.597l0.7-3.22h-2.46l-0.7 3.22h-1.592l1.613-7.46h1.597l-0.632 2.924h2.459l0.632-2.924h1.592l-1.613 7.46zM46.319 9.831c0 0.963-0.172 1.824-0.517 2.585s-0.816 1.334-1.415 1.722c-0.598 0.388-1.288 0.582-2.067 0.582-0.891 0-1.587-0.251-2.086-0.753s-0.749-1.198-0.749-2.090c0-0.902 0.172-1.731 0.517-2.488s0.82-1.338 1.425-1.743c0.605-0.405 1.306-0.607 2.099-0.607 0.888 0 1.575 0.245 2.063 0.735s0.73 1.176 0.73 2.056zM43.395 8.356c-0.421 0-0.808 0.155-1.159 0.467s-0.627 0.739-0.828 1.283-0.3 1.135-0.3 1.771c0 0.5 0.116 0.877 0.348 1.133s0.558 0.383 0.979 0.383 0.805-0.148 1.151-0.444c0.346-0.296 0.617-0.714 0.812-1.255s0.292-1.148 0.292-1.822c0-0.483-0.113-0.856-0.339-1.12-0.227-0.264-0.546-0.396-0.957-0.396zM53.427 14.618h-1.786l-1.859-5.644h-0.031l-0.021 0.163c-0.111 0.735-0.227 1.391-0.344 1.97l-0.757 3.511h-1.436l1.613-7.46h1.864l1.775 5.496h0.021c0.042-0.259 0.109-0.628 0.203-1.107s0.407-1.942 0.94-4.388h1.43l-1.613 7.461zM13.296 20.185c0 0.98-0.177 1.832-0.532 2.556s-0.868 1.274-1.539 1.652c-0.672 0.379-1.464 0.568-2.376 0.568h-2.449l1.678-7.68h2.15c0.977 0 1.733 0.25 2.267 0.751s0.801 1.219 0.801 2.154zM8.925 23.615c0.536 0 1.003-0.133 1.401-0.399s0.71-0.657 0.934-1.174c0.225-0.517 0.337-1.108 0.337-1.773 0-0.54-0.131-0.95-0.394-1.232s-0.64-0.423-1.132-0.423h-0.624l-1.097 5.001h0.575zM18.64 24.96h-4.436l1.678-7.68h4.442l-0.293 1.334h-2.78l-0.364 1.686h2.59l-0.299 1.334h-2.59l-0.435 1.98h2.78l-0.293 1.345zM20.509 24.96l1.678-7.68h1.661l-1.39 6.335h2.78l-0.294 1.345h-4.436zM26.547 24.96l1.694-7.68h1.656l-1.694 7.68h-1.656zM33.021 23.389c0.282-0.774 0.481-1.27 0.597-1.487l2.346-4.623h1.716l-4.061 7.68h-1.814l-0.689-7.68h1.602l0.277 4.623c0.015 0.157 0.022 0.39 0.022 0.699-0.007 0.361-0.018 0.623-0.033 0.788h0.038zM41.678 24.96h-4.437l1.678-7.68h4.442l-0.293 1.334h-2.78l-0.364 1.686h2.59l-0.299 1.334h-2.59l-0.435 1.98h2.78l-0.293 1.345zM45.849 22.013l-0.646 2.947h-1.656l1.678-7.68h1.949c0.858 0 1.502 0.179 1.933 0.536s0.646 0.881 0.646 1.571c0 0.554-0.15 1.029-0.451 1.426s-0.733 0.692-1.298 0.885l1.417 3.263h-1.803l-1.124-2.947h-0.646zM46.137 20.689h0.424c0.474 0 0.843-0.1 1.108-0.3s0.396-0.504 0.396-0.914c0-0.287-0.086-0.502-0.258-0.646s-0.442-0.216-0.812-0.216h-0.402l-0.456 2.076zM53.712 20.39l2.031-3.11h1.857l-3.355 4.744-0.646 2.936h-1.645l0.646-2.936-1.281-4.744h1.694l0.7 3.11z"></path>
</svg>
</div></div>  </div>
  </div>

</li>
            </ul>
          </div>

      </div>
     
            <div class="container"><div class="top-divider full-width"></div></div>
      </div>
<div class="header-bg-container fill"><div class="header-bg-image fill"></div><div class="header-bg-color fill"></div></div>		</div>
	</header>

	
	<main id="main" class="">


<div id="content" role="main" class="content-area">

		
			
<div class="slider-wrapper relative" id="slider-1430498905" >
    <div class="slider slider-nav-circle slider-nav-large slider-nav-light slider-style-normal"
        data-flickity-options='{
            "cellAlign": "center",
            "imagesLoaded": true,
            "lazyLoad": 1,
            "freeScroll": false,
            "wrapAround": true,
            "autoPlay": 6000,
            "pauseAutoPlayOnHover" : true,
            "prevNextButtons": true,
            "contain" : true,
            "adaptiveHeight" : true,
            "dragThreshold" : 10,
            "percentPosition": true,
            "pageDots": true,
            "rightToLeft": false,
            "draggable": true,
            "selectedAttraction": 0.1,
            "parallax" : 0,
            "friction": 0.6        }'
        >
        


  <div class="banner has-hover" id="banner-474653540">
          <div class="banner-inner fill">
        <div class="banner-bg fill" >
            <div class="bg fill bg-fill "></div>
                        <div class="overlay"></div>            
                    </div>
        <div class="banner-layers container">
            <div class="fill banner-link"></div>            

   <div id="text-box-1823522292" class="text-box banner-layer x50 md-x50 lg-x50 y50 md-y50 lg-y50 res-text">
                     <div data-animate="flipInY">           <div class="text-box-content text dark">
              
              <div class="text-inner text-center">
                  

<h3 class="alt-font">It has Finally started&#8230;</h3>
<div class="is-divider divider clearfix" style="margin-top:3px;margin-bottom:3px;"></div>

<h1 class="h-large uppercase"><span style="font-size: 160%;"><strong>HUGE SALE</strong></span></h1>
<h1 class="uppercase"><span style="font-size: 100%;">UP TO <strong>70% OFF</strong></span></h1>
<div class="is-divider divider clearfix" ></div>

<a href="#" target="_self" class="button white is-outline"  >
    <span>Shop men</span>
  </a>


<a href="#" target="_self" class="button white is-outline"  >
    <span>Shop women</span>
  </a>


<a href="#" target="_self" class="button white is-outline"  >
    <span>Shop all</span>
  </a>



              </div>
           </div>
       </div>                     
<style>
#text-box-1823522292 {
  width: 100%;
}
#text-box-1823522292 .text-box-content {
  font-size: 100%;
}
@media (min-width:550px) {
  #text-box-1823522292 {
    width: 70%;
  }
}
</style>
    </div>
 
	<div class="img has-hover x50 md-x50 lg-x50 y50 md-y50 lg-y50" id="image_1910647265">
								<div class="img-inner dark" >
			<img width="700" height="421" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/osSectionsLight.jpg" class="attachment-large size-large" alt="" loading="lazy" srcset="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/osSectionsLight.jpg 700w, http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/osSectionsLight-665x400.jpg 665w, http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/osSectionsLight-510x307.jpg 510w" sizes="(max-width: 700px) 100vw, 700px" />						
					</div>
								
<style>
#image_1910647265 {
  width: 100%;
}
</style>
	</div>
	


        </div>
      </div>

            
<style>
#banner-474653540 {
  padding-top: 600px;
}
#banner-474653540 .bg.bg-loaded {
  background-image: url(http://127.0.0.1:82/wordpress/wp-content/uploads/2021/01/صورة-تخرج.jpg);
}
#banner-474653540 .overlay {
  background-color: rgba(0, 0, 0, 0.02);
}
#banner-474653540 .bg {
  background-position: 58% 63%;
}
</style>
  </div>



  <div class="banner has-hover" id="banner-1875635870">
          <div class="banner-inner fill">
        <div class="banner-bg fill" >
            <div class="bg fill bg-fill "></div>
                        <div class="overlay"></div>            
                    </div>
        <div class="banner-layers container">
            <div class="fill banner-link"></div>            

   <div id="text-box-540237418" class="text-box banner-layer x50 md-x10 lg-x10 y50 md-y50 lg-y50 res-text">
                     <div data-animate="fadeInLeft">           <div class="text-box-content text ">
              
              <div class="text-inner text-center">
                  


<div class="is-divider divider clearfix" ></div>

<a class="button primary is-outline"  >
    <span>auctionsin</span>
  </a>



              </div>
           </div>
       </div>                     
<style>
#text-box-540237418 {
  width: 85%;
}
#text-box-540237418 .text-box-content {
  font-size: 100%;
}
@media (min-width:550px) {
  #text-box-540237418 {
    width: 40%;
  }
}
</style>
    </div>
 

        </div>
      </div>

            
<style>
#banner-1875635870 {
  padding-top: 600px;
}
#banner-1875635870 .bg.bg-loaded {
  background-image: url(http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/120588.jpg);
}
#banner-1875635870 .overlay {
  background-color: rgba(0, 0, 0, 0.03);
}
#banner-1875635870 .bg {
  background-position: 74% 5%;
}
</style>
  </div>



  <div class="banner has-hover" id="banner-1714553269">
          <div class="banner-inner fill">
        <div class="banner-bg fill" >
            <div class="bg fill bg-fill "></div>
                        <div class="overlay"></div>            
                    </div>
        <div class="banner-layers container">
            <div class="fill banner-link"></div>            

   <div id="text-box-1814706417" class="text-box banner-layer x10 md-x10 lg-x10 y50 md-y50 lg-y50 res-text">
                     <div data-animate="fadeInLeft">           <div class="text-box-content text ">
              
              <div class="text-inner text-left">
                  

<p style="text-align: center;"><span style="font-size: 160%;"><strong>تسوق</strong></span></p>
<div class="is-divider divider clearfix" ></div>


              </div>
           </div>
       </div>                     
<style>
#text-box-1814706417 {
  width: 84%;
}
#text-box-1814706417 .text-box-content {
  font-size: 100%;
}
@media (min-width:550px) {
  #text-box-1814706417 {
    width: 40%;
  }
}
</style>
    </div>
 

        </div>
      </div>

            
<style>
#banner-1714553269 {
  padding-top: 600px;
}
#banner-1714553269 .bg.bg-loaded {
  background-image: url(http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/60-111151-lamborghini-veneno-recall-fire_700x400.jpeg);
}
#banner-1714553269 .overlay {
  background-color: rgba(0, 0, 0, 0.03);
}
#banner-1714553269 .bg {
  background-position: 57% 49%;
}
</style>
  </div>



     </div>

     <div class="loading-spin dark large centered"></div>

     	</div>



  
    <div class="row large-columns-4 medium-columns-3 small-columns-2 row-small slider row-slider slider-nav-reveal slider-nav-push"  data-flickity-options='{"imagesLoaded": true, "groupCells": "100%", "dragThreshold" : 5, "cellAlign": "left","wrapAround": true,"prevNextButtons": true,"percentPosition": true,"pageDots": false, "rightToLeft": false, "autoPlay" : false}'>

  	</div>

<div class="container section-title-container" ><h3 class="section-title section-title-center"><b></b><span class="section-title-main" >Best Selling Products</span><b></b></h3></div>

<div class="container section-title-container" ><h3 class="section-title section-title-center"><b></b><span class="section-title-main" >The latest</span><b></b></h3></div>

<div class="container section-title-container" ><h3 class="section-title section-title-center"><b></b><span class="section-title-main" >Featured products</span><b></b></h3></div>


  
    <div class="row large-columns-4 medium-columns-3 small-columns-2 row-small slider row-slider slider-nav-reveal slider-nav-push"  data-flickity-options='{"imagesLoaded": true, "groupCells": "100%", "dragThreshold" : 5, "cellAlign": "left","wrapAround": true,"prevNextButtons": true,"percentPosition": true,"pageDots": false, "rightToLeft": false, "autoPlay" : false}'>

  	
	     
					
<div class="product-small col has-hover uwa_auction_status_expired product type-product post-1024 status-publish first instock product_cat-25 has-post-thumbnail sold-individually shipping-taxable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=opel">
					<img width="247" height="149" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/امجد-247x149.png" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1024  wishlist-fragment on-first-load" data-fragment-ref="1024" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1024,&quot;parent_product_id&quot;:1024,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1024" rel="nofollow" data-product-id="1024" data-product-type="auction" data-original-product-id="1024" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1024" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=opel" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">opel</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-sold-for sold_for">Sold for</span>: <span class="woocommerce-Price-amount amount"><bdi><span class="woocommerce-Price-currencySymbol">&#x62f;.&#x627;</span>5,000.00</bdi></span></span>
</div>		</div>
	</div>
			</div>
</div>
	            
					
<div class="product-small col has-hover uwa_auction_status_expired product type-product post-1028 status-publish instock product_cat-25 has-post-thumbnail sold-individually shipping-taxable purchasable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=%d9%85%d8%b1%d8%b3%d9%8a%d8%af%d8%b3-%d8%ac%d9%8a-%d9%83%d9%84%d8%a7%d8%b3-2019">
					<img width="247" height="169" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/مرسيدس-2019-247x169.jpg" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1028  wishlist-fragment on-first-load" data-fragment-ref="1028" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1028,&quot;parent_product_id&quot;:1028,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1028" rel="nofollow" data-product-id="1028" data-product-type="auction" data-original-product-id="1028" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1028" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=%d9%85%d8%b1%d8%b3%d9%8a%d8%af%d8%b3-%d8%ac%d9%8a-%d9%83%d9%84%d8%a7%d8%b3-2019" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">مرسيدس جي كلاس 2019</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-winned-for winning_bid">Winning Bid</span>: <span class="woocommerce-Price-amount amount"><bdi><span class="woocommerce-Price-currencySymbol">&#x62f;.&#x627;</span>101.00</bdi></span></span>
</div>		</div>
	</div>
			<a href="http://127.0.0.1:82/wordpress/?page_id=682&amp;pay-uwa-auction=1028" class="button">Pay Now</a>
			</div>
</div>
	            
					
<div class="product-small col has-hover uwa_auction_status_expired product type-product post-1030 status-publish last instock product_cat-25 has-post-thumbnail sold-individually shipping-taxable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=%d9%81%d9%88%d8%b1%d8%af-%d9%85%d9%88%d8%b3%d8%aa%d9%86%d8%ac-2015">
					<img width="247" height="183" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/فورد-موستنج-247x183.jpg" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1030  wishlist-fragment on-first-load" data-fragment-ref="1030" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1030,&quot;parent_product_id&quot;:1030,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1030" rel="nofollow" data-product-id="1030" data-product-type="auction" data-original-product-id="1030" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1030" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=%d9%81%d9%88%d8%b1%d8%af-%d9%85%d9%88%d8%b3%d8%aa%d9%86%d8%ac-2015" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">فورد موستنج 2015</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-winned-for expired">Auction Expired</span> </span>
</div>		</div>
	</div>
			</div>
</div>
	            
					
<div class="product-small col has-hover uwa_auction_status_expired product type-product post-1032 status-publish first instock product_cat-25 has-post-thumbnail sold-individually shipping-taxable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=%d8%ac%d9%8a%d8%a8-2015">
					<img width="247" height="174" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/jep-2018-247x174.jpg" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1032  wishlist-fragment on-first-load" data-fragment-ref="1032" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1032,&quot;parent_product_id&quot;:1032,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1032" rel="nofollow" data-product-id="1032" data-product-type="auction" data-original-product-id="1032" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1032" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=%d8%ac%d9%8a%d8%a8-2015" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">جيب 2015</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-winned-for expired">Auction Expired</span> </span>
</div>		</div>
	</div>
			</div>
</div>
	            
					
<div class="product-small col has-hover uwa_auction_status_live product type-product post-1035 status-publish instock product_cat-25 has-post-thumbnail sold-individually shipping-taxable purchasable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=jep-2018">
					<img width="247" height="174" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/jep-2018-247x174.jpg" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1035  wishlist-fragment on-first-load" data-fragment-ref="1035" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1035,&quot;parent_product_id&quot;:1035,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1035" rel="nofollow" data-product-id="1035" data-product-type="auction" data-original-product-id="1035" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1035" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><span class="uwa_winning" data-auction_id="1035" data-user_id="1">Winning!</span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=jep-2018" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">jep 2018</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-auction-price current-bid" data-auction-id="1035" data-bid="5000" data-status="running"><span class="woo-ua-current auction">Current bid</span>: <span class="woocommerce-Price-amount amount"><bdi><span class="woocommerce-Price-currencySymbol">&#x62f;.&#x627;</span>5,000.00</bdi></span></span></span>
</div>		</div>
	</div>
			</div>
</div>
	            
					
<div class="product-small col has-hover uwa_auction_status_live product type-product post-1050 status-publish last instock product_cat-25 product_tag-192 has-post-thumbnail sold-individually shipping-taxable purchasable product-type-auction">
	<div class="col-inner">
	
<div class="badge-container absolute left top z-1">
</div>
	<div class="product-small box ">
		<div class="box-image">
			<div class="image-fade_in_back">
				<a href="http://127.0.0.1:82/wordpress/?product=mercedes-benz-amg-gt-2015">
					<img width="247" height="169" src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Mercedes-Benz-AMG-GT-247x169.jpg" class="attachment-woocommerce_thumbnail size-woocommerce_thumbnail" alt="" loading="lazy" />				</a>
			</div>
			<div class="image-tools is-small top right show-on-hover">
						<div class="wishlist-icon">
			<button class="wishlist-button button is-outline circle icon" aria-label="Wishlist">
				<i class="icon-heart" ></i>			</button>
			<div class="wishlist-popup dark">
				
<div class="yith-wcwl-add-to-wishlist add-to-wishlist-1050  wishlist-fragment on-first-load" data-fragment-ref="1050" data-fragment-options="{&quot;base_url&quot;:&quot;&quot;,&quot;in_default_wishlist&quot;:false,&quot;is_single&quot;:false,&quot;show_exists&quot;:false,&quot;product_id&quot;:1050,&quot;parent_product_id&quot;:1050,&quot;product_type&quot;:&quot;auction&quot;,&quot;show_view&quot;:false,&quot;browse_wishlist_text&quot;:&quot;Browse wishlist&quot;,&quot;already_in_wishslist_text&quot;:&quot;The product is already in your wishlist!&quot;,&quot;product_added_text&quot;:&quot;Product added!&quot;,&quot;heading_icon&quot;:&quot;fa-heart-o&quot;,&quot;available_multi_wishlist&quot;:false,&quot;disable_wishlist&quot;:false,&quot;show_count&quot;:false,&quot;ajax_loading&quot;:false,&quot;loop_position&quot;:&quot;after_add_to_cart&quot;,&quot;item&quot;:&quot;add_to_wishlist&quot;}">
			
			<!-- ADD TO WISHLIST -->
			
<div class="yith-wcwl-add-button">
	<a href="?add_to_wishlist=1050" rel="nofollow" data-product-id="1050" data-product-type="auction" data-original-product-id="1050" class="add_to_wishlist single_add_to_wishlist" data-title="Add to wishlist">
		<i class="yith-wcwl-icon fa fa-heart-o"></i>		<span>Add to wishlist</span>
	</a>
</div>
			<!-- COUNT TEXT -->
			
			</div>			</div>
		</div>
					</div>
			<div class="image-tools is-small hide-for-small bottom left show-on-hover">
							</div>
			<div class="image-tools grid-tools text-center hide-for-small bottom hover-slide-in show-on-hover">
				  <a class="quick-view" data-prod="1050" href="#quick-view">Quick View</a>			</div>
					</div>

		<div class="box-text box-text-products text-center grid-style-2">
			<span class="uwa_auction_bage_icon"  ></span><div class="title-wrapper">		<p class="category uppercase is-smaller no-text-overflow product-cat op-7">
			مزادات		</p>
	<p class="name product-title woocommerce-loop-product__title"><a href="http://127.0.0.1:82/wordpress/?product=mercedes-benz-amg-gt-2015" class="woocommerce-LoopProduct-link woocommerce-loop-product__link">Mercedes-Benz AMG GT 2015</a></p></div><div class="price-wrapper">
	<span class="price"><span class="woo-ua-auction-price starting-bid" data-auction-id="1050" data-bid="" data-status="running"><span class="woo-ua-current auction">Starting bid</span>: <span class="woocommerce-Price-amount amount"><bdi><span class="woocommerce-Price-currencySymbol">&#x62f;.&#x627;</span>1.00</bdi></span></span></span>
</div>		</div>
	</div>
			</div>
</div>
	            	        </div>

<div class="container section-title-container" ><h3 class="section-title section-title-center"><b></b><span class="section-title-main" >Browse our categories</span><b></b></h3></div>


  
    <div class="row large-columns-4 medium-columns-3 small-columns-2 row-small slider row-slider slider-nav-reveal"  data-flickity-options='{"imagesLoaded": true, "groupCells": "100%", "dragThreshold" : 5, "cellAlign": "left","wrapAround": true,"prevNextButtons": true,"percentPosition": true,"pageDots": false, "rightToLeft": false, "autoPlay" : false}'>

          <div class="product-category col" >
            <div class="col-inner">
              <a href="http://127.0.0.1:82/wordpress/?product_cat=%d9%85%d8%b2%d8%a7%d8%af%d8%a7%d8%aa">                <div class="box box-category has-hover box-badge hover-dark ">
                <div class="box-image" >
                  <div class="" >
                  <img src="http://127.0.0.1:82/wordpress/wp-content/uploads/2021/04/Auction512-247x296.jpg" alt="مزادات" width="300" height="300" />                                                      </div>
                </div>
                <div class="box-text text-center" >
                  <div class="box-text-inner">
                      <h5 class="uppercase header-title">
                              مزادات                      </h5>
                                            <p class="is-xsmall uppercase count ">
	                      6 Products                      </p>
                                            
                  </div>
                </div>
                </div>
            </a>            </div>
            </div>
        </div>

	<div id="gap-651775188" class="gap-element clearfix" style="display:block; height:auto;">
		
<style>
#gap-651775188 {
  padding-top: 40px;
}
</style>
	</div>
	

<div class="slider-wrapper relative" id="slider-166247266" >
    <div class="slider slider-nav-circle slider-nav-large slider-nav-light slider-style-normal"
        data-flickity-options='{
            "cellAlign": "center",
            "imagesLoaded": true,
            "lazyLoad": 1,
            "freeScroll": false,
            "wrapAround": true,
            "autoPlay": 2000,
            "pauseAutoPlayOnHover" : true,
            "prevNextButtons": true,
            "contain" : true,
            "adaptiveHeight" : true,
            "dragThreshold" : 10,
            "percentPosition": true,
            "pageDots": true,
            "rightToLeft": false,
            "draggable": true,
            "selectedAttraction": 0.1,
            "parallax" : 0,
            "friction": 0.6        }'
        >
        


  <div class="banner has-hover has-parallax" id="banner-1449366874">
          <div class="banner-inner fill">
        <div class="banner-bg fill" data-parallax="-1" data-parallax-container=".banner" data-parallax-background>
            <div class="bg fill bg-fill "></div>
                                    
                    </div>
        <div class="banner-layers container">
            <div class="fill banner-link"></div>            

   <div id="text-box-952343159" class="text-box banner-layer x50 md-x50 lg-x50 y50 md-y50 lg-y50 res-text">
                                <div class="text-box-content text dark">
              
              <div class="text-inner text-center">
                  

  <div class="icon-box testimonial-box icon-box-left text-left">
                <div class="icon-box-text p-last-0">
          <div class="star-rating"><span style="width:55%"><strong class="rating"></strong></span></div>  				<div class="testimonial-text line-height-small italic test_text first-reset last-reset is-italic">
            

<p>PBR kogi VHS commodo, single-origin coffee selvage kale chips. Fugiat try-hard ad aesthetic, tofu master cleanse typewriter tote bag accusamus sustainable ennui hella small batch cliche.</p>

          </div>
          <div class="testimonial-meta pt-half">
             <strong class="testimonial-name test_name">Lucy Anderson</strong>
             <span class="testimonial-name-divider"> / </span>             <span class="testimonial-company test_company">Facebook</span>
          </div>
        </div>
  </div>

  

              </div>
           </div>
                            
<style>
#text-box-952343159 {
  width: 78%;
}
#text-box-952343159 .text-box-content {
  font-size: 100%;
}
</style>
    </div>
 

        </div>
      </div>

            
<style>
#banner-1449366874 {
  padding-top: 300px;
}
#banner-1449366874 .bg.bg-loaded {
  background-image: url(http://127.0.0.1:82/wordpress/wp-content/uploads/2016/08/dummy-2-1.jpg);
}
</style>
  </div>



  <div class="banner has-hover has-parallax" id="banner-2144753220">
          <div class="banner-inner fill">
        <div class="banner-bg fill" data-parallax="-1" data-parallax-container=".banner" data-parallax-background>
            <div class="bg fill bg-fill "></div>
                                    
                    </div>
        <div class="banner-layers container">
            <div class="fill banner-link"></div>            

   <div id="text-box-1566810031" class="text-box banner-layer x50 md-x50 lg-x50 y50 md-y50 lg-y50 res-text">
                                <div class="text-box-content text dark">
              
              <div class="text-inner text-center">
                  

  <div class="icon-box testimonial-box icon-box-left text-left">
                <div class="icon-box-text p-last-0">
          <div class="star-rating"><span style="width:55%"><strong class="rating"></strong></span></div>  				<div class="testimonial-text line-height-small italic test_text first-reset last-reset is-italic">
            

<p>PBR kogi VHS commodo, single-origin coffee selvage kale chips. Fugiat try-hard ad aesthetic, tofu master cleanse typewriter tote bag accusamus sustainable ennui hella small batch cliche.</p>

          </div>
          <div class="testimonial-meta pt-half">
             <strong class="testimonial-name test_name">Rebecca Smith</strong>
             <span class="testimonial-name-divider"> / </span>             <span class="testimonial-company test_company">Twitter</span>
          </div>
        </div>
  </div>

  

              </div>
           </div>
                            
<style>
#text-box-1566810031 {
  width: 80%;
}
#text-box-1566810031 .text-box-content {
  font-size: 100%;
}
</style>
    </div>
 

        </div>
      </div>

            
<style>
#banner-2144753220 {
  padding-top: 300px;
}
#banner-2144753220 .bg.bg-loaded {
  background-image: url(http://127.0.0.1:82/wordpress/wp-content/uploads/2016/08/dummy-2-1.jpg);
}
</style>
  </div>



     </div>

     <div class="loading-spin dark large centered"></div>

     	</div>


	<div id="text-565253979" class="text">
		

<div class="wp-block-jetpack-send-a-message">
<p style="text-align: center;"><span style="vertical-align: inherit;"><span style="vertical-align: inherit;"><span style="background-color: #00a859;"><a class="whatsapp-block__button" style="background-color: #25d366; color: #fff;" href="https://api.whatsapp.com/send?phone=962799291702&amp;text=%D9%85%D8%B1%D8%AD%D8%A8%D8%A7%20%D9%83%D9%8A%D9%81%20%D9%8A%D9%85%D9%83%D9%86%D9%86%D9%8A%20%D9%85%D8%B3%D8%A7%D8%B9%D8%AF%D8%AA%D9%83" target="_blank" rel="noopener noreferrer"><img loading="lazy" class="wp-image-963" src="http://localhost:82/wordpress/wp-content/uploads/2021/01/تنزيل.jpg" alt="" width="78" height="48" /></a></span></span></span></p>
</div>
		
<style>
#text-565253979 {
  font-size: 1.5rem;
  line-height: 1.75;
  text-align: center;
}
</style>
	</div>
	

		
				
</div>



</main>

<footer id="footer" class="footer-wrapper">

	<div class="block-edit-link" data-title="Edit Block: Demos"   data-backend="http://127.0.0.1:82/wordpress/wp-admin/post.php?post=157&#038;action=edit" data-link="http://127.0.0.1:82/wordpress/wp-admin/post.php?post=696&#038;action=edit&#038;app=uxbuilder&#038;type=editor&#038;edit_post_id=157"></div><div class="social-icons follow-icons" ><a href="https://www.facebook.com/amjadbooksdp" target="_blank" data-label="Facebook"  rel="noopener noreferrer nofollow" class="icon button circle is-outline facebook tooltip" title="Follow on Facebook"><i class="icon-facebook" ></i></a><a href="https://twitter.com/daramjadbooks" target="_blank"  data-label="Twitter"  rel="noopener noreferrer nofollow" class="icon button circle is-outline  twitter tooltip" title="Follow on Twitter"><i class="icon-twitter" ></i></a><a href="mailto:your@email" data-label="E-mail"  rel="nofollow" class="icon button circle is-outline  email tooltip" title="Send us an email"><i class="icon-envelop" ></i></a></div>
<div class="absolute-footer dark medium-text-center text-center">
  <div class="container clearfix">

          <div class="footer-secondary pull-right">
                <div class="payment-icons inline-block"><div class="payment-icon"><svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 64 32">
<path d="M35.255 12.078h-2.396c-0.229 0-0.444 0.114-0.572 0.303l-3.306 4.868-1.4-4.678c-0.088-0.292-0.358-0.493-0.663-0.493h-2.355c-0.284 0-0.485 0.28-0.393 0.548l2.638 7.745-2.481 3.501c-0.195 0.275 0.002 0.655 0.339 0.655h2.394c0.227 0 0.439-0.111 0.569-0.297l7.968-11.501c0.191-0.275-0.006-0.652-0.341-0.652zM19.237 16.718c-0.23 1.362-1.311 2.276-2.691 2.276-0.691 0-1.245-0.223-1.601-0.644-0.353-0.417-0.485-1.012-0.374-1.674 0.214-1.35 1.313-2.294 2.671-2.294 0.677 0 1.227 0.225 1.589 0.65 0.365 0.428 0.509 1.027 0.404 1.686zM22.559 12.078h-2.384c-0.204 0-0.378 0.148-0.41 0.351l-0.104 0.666-0.166-0.241c-0.517-0.749-1.667-1-2.817-1-2.634 0-4.883 1.996-5.321 4.796-0.228 1.396 0.095 2.731 0.888 3.662 0.727 0.856 1.765 1.212 3.002 1.212 2.123 0 3.3-1.363 3.3-1.363l-0.106 0.662c-0.040 0.252 0.155 0.479 0.41 0.479h2.147c0.341 0 0.63-0.247 0.684-0.584l1.289-8.161c0.040-0.251-0.155-0.479-0.41-0.479zM8.254 12.135c-0.272 1.787-1.636 1.787-2.957 1.787h-0.751l0.527-3.336c0.031-0.202 0.205-0.35 0.41-0.35h0.345c0.899 0 1.747 0 2.185 0.511 0.262 0.307 0.341 0.761 0.242 1.388zM7.68 7.473h-4.979c-0.341 0-0.63 0.248-0.684 0.584l-2.013 12.765c-0.040 0.252 0.155 0.479 0.41 0.479h2.378c0.34 0 0.63-0.248 0.683-0.584l0.543-3.444c0.053-0.337 0.343-0.584 0.683-0.584h1.575c3.279 0 5.172-1.587 5.666-4.732 0.223-1.375 0.009-2.456-0.635-3.212-0.707-0.832-1.962-1.272-3.628-1.272zM60.876 7.823l-2.043 12.998c-0.040 0.252 0.155 0.479 0.41 0.479h2.055c0.34 0 0.63-0.248 0.683-0.584l2.015-12.765c0.040-0.252-0.155-0.479-0.41-0.479h-2.299c-0.205 0.001-0.379 0.148-0.41 0.351zM54.744 16.718c-0.23 1.362-1.311 2.276-2.691 2.276-0.691 0-1.245-0.223-1.601-0.644-0.353-0.417-0.485-1.012-0.374-1.674 0.214-1.35 1.313-2.294 2.671-2.294 0.677 0 1.227 0.225 1.589 0.65 0.365 0.428 0.509 1.027 0.404 1.686zM58.066 12.078h-2.384c-0.204 0-0.378 0.148-0.41 0.351l-0.104 0.666-0.167-0.241c-0.516-0.749-1.667-1-2.816-1-2.634 0-4.883 1.996-5.321 4.796-0.228 1.396 0.095 2.731 0.888 3.662 0.727 0.856 1.765 1.212 3.002 1.212 2.123 0 3.3-1.363 3.3-1.363l-0.106 0.662c-0.040 0.252 0.155 0.479 0.41 0.479h2.147c0.341 0 0.63-0.247 0.684-0.584l1.289-8.161c0.040-0.252-0.156-0.479-0.41-0.479zM43.761 12.135c-0.272 1.787-1.636 1.787-2.957 1.787h-0.751l0.527-3.336c0.031-0.202 0.205-0.35 0.41-0.35h0.345c0.899 0 1.747 0 2.185 0.511 0.261 0.307 0.34 0.761 0.241 1.388zM43.187 7.473h-4.979c-0.341 0-0.63 0.248-0.684 0.584l-2.013 12.765c-0.040 0.252 0.156 0.479 0.41 0.479h2.554c0.238 0 0.441-0.173 0.478-0.408l0.572-3.619c0.053-0.337 0.343-0.584 0.683-0.584h1.575c3.279 0 5.172-1.587 5.666-4.732 0.223-1.375 0.009-2.456-0.635-3.212-0.707-0.832-1.962-1.272-3.627-1.272z"></path>
</svg>
</div><div class="payment-icon"><svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 64 32">
<path d="M13.043 8.356c-0.46 0-0.873 0.138-1.24 0.413s-0.662 0.681-0.885 1.217c-0.223 0.536-0.334 1.112-0.334 1.727 0 0.568 0.119 0.99 0.358 1.265s0.619 0.413 1.141 0.413c0.508 0 1.096-0.131 1.765-0.393v1.327c-0.693 0.262-1.389 0.393-2.089 0.393-0.884 0-1.572-0.254-2.063-0.763s-0.736-1.229-0.736-2.161c0-0.892 0.181-1.712 0.543-2.462s0.846-1.32 1.452-1.709 1.302-0.584 2.089-0.584c0.435 0 0.822 0.038 1.159 0.115s0.7 0.217 1.086 0.421l-0.616 1.276c-0.369-0.201-0.673-0.333-0.914-0.398s-0.478-0.097-0.715-0.097zM19.524 12.842h-2.47l-0.898 1.776h-1.671l3.999-7.491h1.948l0.767 7.491h-1.551l-0.125-1.776zM19.446 11.515l-0.136-1.786c-0.035-0.445-0.052-0.876-0.052-1.291v-0.184c-0.153 0.408-0.343 0.84-0.569 1.296l-0.982 1.965h1.739zM27.049 12.413c0 0.711-0.257 1.273-0.773 1.686s-1.213 0.62-2.094 0.62c-0.769 0-1.389-0.153-1.859-0.46v-1.398c0.672 0.367 1.295 0.551 1.869 0.551 0.39 0 0.694-0.072 0.914-0.217s0.329-0.343 0.329-0.595c0-0.147-0.024-0.275-0.070-0.385s-0.114-0.214-0.201-0.309c-0.087-0.095-0.303-0.269-0.648-0.52-0.481-0.337-0.818-0.67-1.013-1s-0.293-0.685-0.293-1.066c0-0.439 0.108-0.831 0.324-1.176s0.523-0.614 0.922-0.806 0.857-0.288 1.376-0.288c0.755 0 1.446 0.168 2.073 0.505l-0.569 1.189c-0.543-0.252-1.044-0.378-1.504-0.378-0.289 0-0.525 0.077-0.71 0.23s-0.276 0.355-0.276 0.607c0 0.207 0.058 0.389 0.172 0.543s0.372 0.36 0.773 0.615c0.421 0.272 0.736 0.572 0.945 0.9s0.313 0.712 0.313 1.151zM33.969 14.618h-1.597l0.7-3.22h-2.46l-0.7 3.22h-1.592l1.613-7.46h1.597l-0.632 2.924h2.459l0.632-2.924h1.592l-1.613 7.46zM46.319 9.831c0 0.963-0.172 1.824-0.517 2.585s-0.816 1.334-1.415 1.722c-0.598 0.388-1.288 0.582-2.067 0.582-0.891 0-1.587-0.251-2.086-0.753s-0.749-1.198-0.749-2.090c0-0.902 0.172-1.731 0.517-2.488s0.82-1.338 1.425-1.743c0.605-0.405 1.306-0.607 2.099-0.607 0.888 0 1.575 0.245 2.063 0.735s0.73 1.176 0.73 2.056zM43.395 8.356c-0.421 0-0.808 0.155-1.159 0.467s-0.627 0.739-0.828 1.283-0.3 1.135-0.3 1.771c0 0.5 0.116 0.877 0.348 1.133s0.558 0.383 0.979 0.383 0.805-0.148 1.151-0.444c0.346-0.296 0.617-0.714 0.812-1.255s0.292-1.148 0.292-1.822c0-0.483-0.113-0.856-0.339-1.12-0.227-0.264-0.546-0.396-0.957-0.396zM53.427 14.618h-1.786l-1.859-5.644h-0.031l-0.021 0.163c-0.111 0.735-0.227 1.391-0.344 1.97l-0.757 3.511h-1.436l1.613-7.46h1.864l1.775 5.496h0.021c0.042-0.259 0.109-0.628 0.203-1.107s0.407-1.942 0.94-4.388h1.43l-1.613 7.461zM13.296 20.185c0 0.98-0.177 1.832-0.532 2.556s-0.868 1.274-1.539 1.652c-0.672 0.379-1.464 0.568-2.376 0.568h-2.449l1.678-7.68h2.15c0.977 0 1.733 0.25 2.267 0.751s0.801 1.219 0.801 2.154zM8.925 23.615c0.536 0 1.003-0.133 1.401-0.399s0.71-0.657 0.934-1.174c0.225-0.517 0.337-1.108 0.337-1.773 0-0.54-0.131-0.95-0.394-1.232s-0.64-0.423-1.132-0.423h-0.624l-1.097 5.001h0.575zM18.64 24.96h-4.436l1.678-7.68h4.442l-0.293 1.334h-2.78l-0.364 1.686h2.59l-0.299 1.334h-2.59l-0.435 1.98h2.78l-0.293 1.345zM20.509 24.96l1.678-7.68h1.661l-1.39 6.335h2.78l-0.294 1.345h-4.436zM26.547 24.96l1.694-7.68h1.656l-1.694 7.68h-1.656zM33.021 23.389c0.282-0.774 0.481-1.27 0.597-1.487l2.346-4.623h1.716l-4.061 7.68h-1.814l-0.689-7.68h1.602l0.277 4.623c0.015 0.157 0.022 0.39 0.022 0.699-0.007 0.361-0.018 0.623-0.033 0.788h0.038zM41.678 24.96h-4.437l1.678-7.68h4.442l-0.293 1.334h-2.78l-0.364 1.686h2.59l-0.299 1.334h-2.59l-0.435 1.98h2.78l-0.293 1.345zM45.849 22.013l-0.646 2.947h-1.656l1.678-7.68h1.949c0.858 0 1.502 0.179 1.933 0.536s0.646 0.881 0.646 1.571c0 0.554-0.15 1.029-0.451 1.426s-0.733 0.692-1.298 0.885l1.417 3.263h-1.803l-1.124-2.947h-0.646zM46.137 20.689h0.424c0.474 0 0.843-0.1 1.108-0.3s0.396-0.504 0.396-0.914c0-0.287-0.086-0.502-0.258-0.646s-0.442-0.216-0.812-0.216h-0.402l-0.456 2.076zM53.712 20.39l2.031-3.11h1.857l-3.355 4.744-0.646 2.936h-1.645l0.646-2.936-1.281-4.744h1.694l0.7 3.11z"></path>
</svg>
</div></div>      </div>
    
    <div class="footer-primary pull-left">
                          <div class="copyright-footer">
        Copyright 2021 © <strong style="color:white; font-size :16px;">كفاءة المعرفة للنشر والتوزيع</strong>       </div>
          </div>
  </div>
</div>
<a href="#top" class="back-to-top button icon invert plain fixed bottom z-1 is-outline left circle" id="top-link"><i class="icon-angle-up" ></i></a>

</footer>

</div>

<div id="main-menu" class="mobile-sidebar no-scrollbar mfp-hide">
	<div class="sidebar-menu no-scrollbar ">
		<ul class="nav nav-sidebar nav-vertical nav-uppercase">
			<li class="header-search-form search-form html relative has-icon">
	<div class="header-search-form-wrapper">
		<div class="searchform-wrapper ux-search-box relative is-normal"><form role="search" method="get" class="searchform" action="http://127.0.0.1:82/wordpress/">
	<div class="flex-row relative">
						<div class="flex-col flex-grow">
			<label class="screen-reader-text" for="woocommerce-product-search-field-1">Search for:</label>
			<input type="search" id="woocommerce-product-search-field-1" class="search-field mb-0" placeholder="Search&hellip;" value="" name="s" />
			<input type="hidden" name="post_type" value="product" />
					</div>
		<div class="flex-col">
			<button type="submit" value="Search" class="ux-search-submit submit-button secondary button icon mb-0" aria-label="Submit">
				<i class="icon-search" ></i>			</button>
		</div>
	</div>
	<div class="live-search-results text-left z-top"></div>
</form>
</div>	</div>
</li><li class="account-item has-icon menu-item">

<a href="" class="account-link account-login" title="My account">
    <span class="header-account-title">
    My account  </span>
</a>


<ul class="children">
    
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--dashboard is-active active">
          <a href="http://127.0.0.1:82/wordpress">Dashboard</a>
      <!-- empty -->
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--orders">
          <a href="http://127.0.0.1:82/wordpress?orders">Orders</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--downloads">
          <a href="http://127.0.0.1:82/wordpress?downloads">Downloads</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--edit-address">
          <a href="http://127.0.0.1:82/wordpress?edit-address">Addresses</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--edit-account">
          <a href="http://127.0.0.1:82/wordpress?edit-account">Account details</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction-setting">
          <a href="http://127.0.0.1:82/wordpress?my-auction-setting">Auctions Setting</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction">
          <a href="http://127.0.0.1:82/wordpress?my-auction">My Auctions</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--my-auction-watchlist">
          <a href="http://127.0.0.1:82/wordpress?my-auction-watchlist">My Auctions Watchlist</a>
        </li>
      <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--customer-logout">
          <a href="http://127.0.0.1:82/wordpress?customer-logout"></a>
        </li>
    		<li class="wishlist-account-element ">
			<a href="/wordpress/?wishlist-action"></a>
		</li>
		  <li class="woocommerce-MyAccount-navigation-link woocommerce-MyAccount-navigation-link--customer-logout">
    <a href="http://127.0.0.1:82/wordpress?customer-logout">Logout</a>
  </li>
</ul>
</li>
<li class="header-newsletter-item has-icon">

  <a href="#header-newsletter-signup" class="tooltip" title="Sign up for Newsletter">

    <i class="icon-envelop"></i>
    <span class="header-newsletter-title">
      Newsletter    </span>
  </a>

</li><li class="html header-social-icons ml-0">
	<div class="social-icons follow-icons" ><a href="https://www.facebook.com/amjadbooksdp" target="_blank" data-label="Facebook"  rel="noopener noreferrer nofollow" class="icon plain facebook tooltip" title="Follow on Facebook"><i class="icon-facebook" ></i></a><a href="https://twitter.com/daramjadbooks" target="_blank"  data-label="Twitter"  rel="noopener noreferrer nofollow" class="icon plain  twitter tooltip" title="Follow on Twitter"><i class="icon-twitter" ></i></a><a href="mailto:your@email" data-label="E-mail"  rel="nofollow" class="icon plain  email tooltip" title="Send us an email"><i class="icon-envelop" ></i></a></div></li><li class="html custom html_topbar_right">أهلاً بك في معرض أمجد بوك للكتب</li>		</ul>
	</div>
</div>
	<script type="text/javascript">
		(function () {
			var c = document.body.className;
			c = c.replace(/woocommerce-no-js/, 'woocommerce-js');
			document.body.className = c;
		})();
	</script>
	<script type="text/template" id="tmpl-variation-template">
	<div class="woocommerce-variation-description">{{{ data.variation.variation_description }}}</div>
	<div class="woocommerce-variation-price">{{{ data.variation.price_html }}}</div>
	<div class="woocommerce-variation-availability">{{{ data.variation.availability_html }}}</div>
</script>
<script type="text/template" id="tmpl-unavailable-variation-template">
	<p>Sorry, this product is unavailable. Please choose a different combination.</p>
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/hoverintent-js.min.js?ver=2.2.1' id='hoverintent-js-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/admin-bar.js?ver=5.7.1' id='admin-bar-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/yith-woocommerce-wishlist/assets/js/jquery.selectBox.min.js?ver=1.2.0' id='jquery-selectBox-js'></script>
<script type='text/javascript' id='jquery-yith-wcwl-js-extra'>
/* <![CDATA[ */
var yith_wcwl_l10n = {"ajax_url":"\/wordpress\/wp-admin\/admin-ajax.php","redirect_to_cart":"no","multi_wishlist":"","hide_add_button":"1","enable_ajax_loading":"","ajax_loader_url":"http:\/\/127.0.0.1:82\/wordpress\/wp-content\/plugins\/yith-woocommerce-wishlist\/assets\/images\/ajax-loader-alt.svg","remove_from_wishlist_after_add_to_cart":"1","is_wishlist_responsive":"1","time_to_close_prettyphoto":"3000","fragments_index_glue":".","reload_on_found_variation":"1","mobile_media_query":"768","labels":{"cookie_disabled":"We are sorry, but this feature is available only if cookies on your browser are enabled.","added_to_cart_message":"<div class=\"woocommerce-notices-wrapper\"><div class=\"woocommerce-message\" role=\"alert\">Product added to cart successfully<\/div><\/div>"},"actions":{"add_to_wishlist_action":"add_to_wishlist","remove_from_wishlist_action":"remove_from_wishlist","reload_wishlist_and_adding_elem_action":"reload_wishlist_and_adding_elem","load_mobile_action":"load_mobile","delete_item_action":"delete_item","save_title_action":"save_title","save_privacy_action":"save_privacy","load_fragments":"load_fragments"}};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/yith-woocommerce-wishlist/assets/js/unminified/jquery.yith-wcwl.js?ver=3.0.20' id='jquery-yith-wcwl-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill.js?ver=7.4.4' id='wp-polyfill-js'></script>
<script type='text/javascript' id='wp-polyfill-js-after'>
( 'fetch' in window ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-fetch.js?ver=3.0.0"></scr' + 'ipt>' );( document.contains ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-node-contains.js?ver=3.42.0"></scr' + 'ipt>' );( window.DOMRect ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-dom-rect.js?ver=3.42.0"></scr' + 'ipt>' );( window.URL && window.URL.prototype && window.URLSearchParams ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-url.js?ver=3.6.4"></scr' + 'ipt>' );( window.FormData && window.FormData.prototype.keys ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-formdata.js?ver=3.0.12"></scr' + 'ipt>' );( Element.prototype.matches && Element.prototype.closest ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-element-closest.js?ver=2.0.2"></scr' + 'ipt>' );( 'objectFit' in document.documentElement.style ) || document.write( '<script src="http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/wp-polyfill-object-fit.js?ver=2.3.4"></scr' + 'ipt>' );
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/hooks.js?ver=50e23bed88bcb9e6e14023e9961698c1' id='wp-hooks-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/i18n.js?ver=db9a9a37da262883343e941c3731bc67' id='wp-i18n-js'></script>
<script type='text/javascript' id='wp-i18n-js-after'>
wp.i18n.setLocaleData( { 'text direction\u0004ltr': [ 'ltr' ] } );
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/vendor/lodash.js?ver=4.17.19' id='lodash-js'></script>
<script type='text/javascript' id='lodash-js-after'>
window.lodash = _.noConflict();
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/url.js?ver=0ac7e0472c46121366e7ce07244be1ac' id='wp-url-js'></script>
<script type='text/javascript' id='wp-api-fetch-js-translations'>
( function( domain, translations ) {
	var localeData = translations.locale_data[ domain ] || translations.locale_data.messages;
	localeData[""].domain = domain;
	wp.i18n.setLocaleData( localeData, domain );
} )( "default", { "locale_data": { "messages": { "": {} } } } );
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/dist/api-fetch.js?ver=a783d1f442d2abefc7d6dbd156a44561' id='wp-api-fetch-js'></script>
<script type='text/javascript' id='wp-api-fetch-js-after'>
wp.apiFetch.use( wp.apiFetch.createRootURLMiddleware( "http://127.0.0.1:82/wordpress/index.php?rest_route=/" ) );
wp.apiFetch.nonceMiddleware = wp.apiFetch.createNonceMiddleware( "26e83e4862" );
wp.apiFetch.use( wp.apiFetch.nonceMiddleware );
wp.apiFetch.use( wp.apiFetch.mediaUploadMiddleware );
wp.apiFetch.nonceEndpoint = "http://127.0.0.1:82/wordpress/wp-admin/admin-ajax.php?action=rest-nonce";
</script>
<script type='text/javascript' id='contact-form-7-js-extra'>
/* <![CDATA[ */
var wpcf7 = [];
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/contact-form-7/includes/js/index.js?ver=5.4' id='contact-form-7-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/jquery-blockui/jquery.blockUI.js?ver=2.70' id='jquery-blockui-js'></script>
<script type='text/javascript' id='wc-add-to-cart-js-extra'>
/* <![CDATA[ */
var wc_add_to_cart_params = {"ajax_url":"\/wordpress\/wp-admin\/admin-ajax.php","wc_ajax_url":"\/wordpress\/?wc-ajax=%%endpoint%%","i18n_view_cart":"View cart","cart_url":"http:\/\/127.0.0.1:82\/wordpress\/?page_id=683","is_cart":"","cart_redirect_after_add":"no"};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/frontend/add-to-cart.js?ver=5.2.2' id='wc-add-to-cart-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/js-cookie/js.cookie.js?ver=2.1.4' id='js-cookie-js'></script>
<script type='text/javascript' id='woocommerce-js-extra'>
/* <![CDATA[ */
var woocommerce_params = {"ajax_url":"\/wordpress\/wp-admin\/admin-ajax.php","wc_ajax_url":"\/wordpress\/?wc-ajax=%%endpoint%%"};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/frontend/woocommerce.js?ver=5.2.2' id='woocommerce-js'></script>
<script type='text/javascript' id='wc-cart-fragments-js-extra'>
/* <![CDATA[ */
var wc_cart_fragments_params = {"ajax_url":"\/wordpress\/wp-admin\/admin-ajax.php","wc_ajax_url":"\/wordpress\/?wc-ajax=%%endpoint%%","cart_hash_key":"wc_cart_hash_c507e0363dc04213d74e32fc829e80af","fragment_name":"wc_fragments_c507e0363dc04213d74e32fc829e80af","request_timeout":"5000"};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/frontend/cart-fragments.js?ver=5.2.2' id='wc-cart-fragments-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/hoverIntent.js?ver=1.8.1' id='hoverIntent-js'></script>
<script type='text/javascript' id='flatsome-js-js-extra'>
/* <![CDATA[ */
var flatsomeVars = {"ajaxurl":"http:\/\/127.0.0.1:82\/wordpress\/wp-admin\/admin-ajax.php","rtl":"","sticky_height":"100","lightbox":{"close_markup":"<button title=\"%title%\" type=\"button\" class=\"mfp-close\"><svg xmlns=\"http:\/\/www.w3.org\/2000\/svg\" width=\"28\" height=\"28\" viewBox=\"0 0 24 24\" fill=\"none\" stroke=\"currentColor\" stroke-width=\"2\" stroke-linecap=\"round\" stroke-linejoin=\"round\" class=\"feather feather-x\"><line x1=\"18\" y1=\"6\" x2=\"6\" y2=\"18\"><\/line><line x1=\"6\" y1=\"6\" x2=\"18\" y2=\"18\"><\/line><\/svg><\/button>","close_btn_inside":false},"user":{"can_edit_pages":true},"i18n":{"mainMenu":"Main Menu"},"options":{"cookie_notice_version":"1"}};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/js/flatsome.js?ver=3.13.3' id='flatsome-js-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/inc/integrations/wc-yith-wishlist/wishlist.js?ver=3.10.2' id='flatsome-woocommerce-wishlist-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/inc/extensions/flatsome-live-search/flatsome-live-search.js?ver=3.13.3' id='flatsome-live-search-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/themes/flatsome/assets/js/woocommerce.js?ver=3.13.3' id='flatsome-theme-woocommerce-js-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/wp-embed.js?ver=5.7.1' id='wp-embed-js'></script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/underscore.min.js?ver=1.8.3' id='underscore-js'></script>
<script type='text/javascript' id='wp-util-js-extra'>
/* <![CDATA[ */
var _wpUtilSettings = {"ajax":{"url":"\/wordpress\/wp-admin\/admin-ajax.php"}};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-includes/js/wp-util.js?ver=5.7.1' id='wp-util-js'></script>
<script type='text/javascript' id='wc-add-to-cart-variation-js-extra'>
/* <![CDATA[ */
var wc_add_to_cart_variation_params = {"wc_ajax_url":"\/wordpress\/?wc-ajax=%%endpoint%%","i18n_no_matching_variations_text":"Sorry, no products matched your selection. Please choose a different combination.","i18n_make_a_selection_text":"Please select some product options before adding this product to your cart.","i18n_unavailable_text":"Sorry, this product is unavailable. Please choose a different combination."};
/* ]]> */
</script>
<script type='text/javascript' src='http://127.0.0.1:82/wordpress/wp-content/plugins/woocommerce/assets/js/frontend/add-to-cart-variation.js?ver=5.2.2' id='wc-add-to-cart-variation-js'></script>

</body>
</html>
