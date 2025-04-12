<script>
	import '../app.css';
	import {Navbar,Footer} from '$lib/index'
	import '@fortawesome/fontawesome-free/css/all.min.css'

	let { children } = $props();
</script>

<Navbar/>
{@render children()}

<Footer/>