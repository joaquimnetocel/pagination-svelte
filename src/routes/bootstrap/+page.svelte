<script lang="ts">
	import { PaginationItems } from '$lib/index.js';

	let stateActivePage = $state(1);
</script>

<svelte:head>
	<link
		href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
		rel="stylesheet"
		integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
		crossorigin="anonymous"
	/>
</svelte:head>

<div class="m-4">
	<nav aria-label="Page navigation example">
		<ul class="pagination">
			<PaginationItems
				propTag="li"
				class="page-item"
				propInnerClass="page-link"
				propDisabledClass="disabled"
				propActiveClass="active"
				propNumberOfRows={28}
				propNumberOfRowsPerPage={5}
				bind:propActivePage={stateActivePage}
			/>
		</ul>
	</nav>
	<div>
		ACTIVE PAGE: {stateActivePage}
	</div>
</div>
