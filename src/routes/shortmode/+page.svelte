<script lang="ts">
	import { PaginationItems } from '$lib/index.js';
	let stateActivePage = $state(1);
</script>

<PaginationItems
	propTag="button"
	propDisabledStyle="background: darkgrey;"
	propActiveStyle="background: blue;color:white;"
	propNumberOfPages={60}
	propShortModeLimit={50}
	bind:propActivePage={stateActivePage}
/>
<p>
	ACTIVE PAGE: {stateActivePage}
</p>
