<script lang="ts">
	import { PaginationItems } from '$lib/index.js';
	let stateActivePage = $state(1);
</script>

<PaginationItems
	propTag="button"
	propDisabledStyle="background: darkgrey;"
	propActiveStyle="background: blue;color:white;"
	propNumberOfRows={28}
	propNumberOfRowsPerPage={5}
	bind:propActivePage={stateActivePage}
/>
<p>
	ACTIVE PAGE: {stateActivePage}
</p>
