<script lang="ts" generics="Generic">
	import { iconBackward } from '$lib/iconBackward.js';
	import { iconFastBackward } from '$lib/iconFastBackward.js';
	import { iconFastForward } from '$lib/iconFastForward.js';
	import { iconForward } from '$lib/iconForward.js';

	let {
		propActivePage = $bindable(1),
		propNumberOfPages = 1,
		propNumberOfRows,
		propNumberOfRowsPerPage,
		propTag,
		propInnerTag = 'span',
		propPrevious = 'PREVIOUS',
		propNext = 'NEXT',
		propDisabledStyle = '',
		propDisabledClass = '',
		propActiveStyle = '',
		propActiveClass = '',
		propInnerStyle = '',
		propInnerClass = '',
		propShortMode = false,
		propShortModeLimit = 1000,
		...propRest
	}: {
		propActivePage?: number;
		propNumberOfPages?: number;
		propNumberOfRows?: number;
		propNumberOfRowsPerPage?: number;
		propTag: 'span' | 'div' | 'li' | 'button' | 'a';
		propInnerTag?: 'span' | 'div' | 'li' | 'button' | 'a';
		propDisabledStyle?: string;
		propDisabledClass?: string;
		propActiveStyle?: string;
		propActiveClass?: string;
		propInnerStyle?: string;
		propInnerClass?: string;
		propPrevious?: string;
		propNext?: string;
		style?: string;
		class?: string;
		propShortMode?: boolean;
		propShortModeLimit?: number;
	} = $props();

	let stateShowInput = $state(false);

	$effect(() => {
		if (propNumberOfRows !== undefined && propNumberOfRowsPerPage !== undefined) {
			propNumberOfPages =
				propNumberOfRowsPerPage === Infinity
					? 1
					: Math.ceil(propNumberOfRows / propNumberOfRowsPerPage);
		}
	});

	let derivedShortMode = $derived(propShortMode === true || propNumberOfPages > propShortModeLimit);

	function functionOnKeyDown(e: { keyCode: number }) {
		switch (e.keyCode) {
			case 13:
				stateShowInput = false;
				break;
		}
	}

	function functionOnInput(event: Event & { currentTarget: EventTarget & HTMLInputElement }) {
		event.currentTarget.value = event.currentTarget.value.replace(/[^0-9]*/g, '');
		if (event.currentTarget.value !== '' && parseInt(event.currentTarget.value)) {
			if (parseInt(event.currentTarget.value) > propNumberOfPages) {
				propActivePage = propNumberOfPages;
				return;
			}
			if (parseInt(event.currentTarget.value) > 0) {
				propActivePage = parseInt(event.currentTarget.value);
			}
		}
	}
</script>

<!-- FAST BACKWARD -->
{#if derivedShortMode}
	{#if propActivePage === 1}
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};${propDisabledStyle};cursor:not-allowed;`}
			class={`${propRest.class ?? ''} ${propDisabledClass}`}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconFastBackward}
				</svelte:element>
			{:else}
				<!-- eslint-disable-next-line svelte/no-at-html-tags -->
				{@html iconFastBackward}
			{/if}
		</svelte:element>
	{:else}
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};cursor:pointer`}
			onclick={() => {
				propActivePage = 1;
			}}
			class={`${propRest.class ?? ''}`}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconBackward}
				</svelte:element>
			{:else}
				<!-- eslint-disable-next-line svelte/no-at-html-tags -->
				{@html iconBackward}
			{/if}
		</svelte:element>
	{/if}
{/if}
<!---->
<!-- PREVIOUS -->
{#if propActivePage === 1}
	<svelte:element
		this={propTag}
		style={`${propRest.style ?? ''};${propDisabledStyle};cursor:not-allowed;`}
		class={`${propRest.class ?? ''} ${propDisabledClass}`}
	>
		{#if propInnerTag}
			<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
				{#if derivedShortMode}
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconBackward}
				{:else}
					{propPrevious}
				{/if}
			</svelte:element>
		{:else if derivedShortMode}
			<!-- eslint-disable-next-line svelte/no-at-html-tags -->
			{@html iconBackward}
		{:else}
			{propPrevious}
		{/if}
	</svelte:element>
{:else}
	<!-- svelte-ignore a11y_no_static_element_interactions -->
	<svelte:element
		this={propTag}
		style={`${propRest.style ?? ''};cursor:pointer`}
		onclick={() => {
			propActivePage = propActivePage - 1;
		}}
		class={`${propRest.class ?? ''}`}
	>
		{#if propInnerTag}
			<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
				{#if derivedShortMode}
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconBackward}
				{:else}
					{propPrevious}
				{/if}
			</svelte:element>
		{:else if derivedShortMode}
			<!-- eslint-disable-next-line svelte/no-at-html-tags -->
			{@html iconBackward}
		{:else}
			{propPrevious}
		{/if}
	</svelte:element>
{/if}
<!---->
{#if derivedShortMode}
	{#if stateShowInput}
		<input
			class={`${propRest.class ?? ''} ${propActiveClass}`}
			style={`${propRest.style ?? ''};${propActiveStyle};${'width:40px;'}`}
			size="1"
			type="number"
			min="1"
			max={propNumberOfPages}
			step="1"
			value={propActivePage}
			onkeydown={functionOnKeyDown}
			oninput={functionOnInput}
			onfocusout={() => {
				stateShowInput = false;
			}}
		/>
	{:else}
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};${propActiveStyle};${'cursor:default;'}`}
			class={`${propRest.class ?? ''} ${propActiveClass}`}
			onclick={() => (stateShowInput = true)}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					{propActivePage}
				</svelte:element>
			{:else}
				{propActivePage}
			{/if}
		</svelte:element>
	{/if}
{:else}
	{#each Array(propNumberOfPages) as _, numberCounter}
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};${propActivePage === numberCounter + 1 ? propActiveStyle : ''};${propActivePage === numberCounter + 1 ? 'cursor:default;' : 'cursor:pointer;'}`}
			class={`${propRest.class ?? ''} ${propActivePage === numberCounter + 1 ? propActiveClass : ''}`}
			onclick={() => {
				propActivePage = numberCounter + 1;
			}}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					{numberCounter + 1}
				</svelte:element>
			{:else}
				{numberCounter + 1}
			{/if}
		</svelte:element>
	{/each}
{/if}
<!-- NEXT -->
{#if propActivePage === propNumberOfPages}
	<svelte:element
		this={propTag}
		style={`${propRest.style ?? ''};${propDisabledStyle};cursor:not-allowed;`}
		class={`${propRest.class ?? ''} ${propDisabledClass}`}
	>
		{#if propInnerTag}
			<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
				{#if derivedShortMode}
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconForward}
				{:else}
					{propNext}
				{/if}
			</svelte:element>
		{:else if derivedShortMode}
			<!-- eslint-disable-next-line svelte/no-at-html-tags -->
			{@html iconForward}
		{:else}
			{propNext}
		{/if}
	</svelte:element>
{:else}
	<!-- svelte-ignore a11y_no_static_element_interactions -->
	<svelte:element
		this={propTag}
		style={`${propRest.style ?? ''};cursor:pointer`}
		class={`${propRest.class ?? ''}`}
		onclick={() => {
			propActivePage = propActivePage + 1;
		}}
	>
		{#if propInnerTag}
			<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
				{#if derivedShortMode}
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconForward}
				{:else}
					{propNext}
				{/if}
			</svelte:element>
		{:else if derivedShortMode}
			<!-- eslint-disable-next-line svelte/no-at-html-tags -->
			{@html iconForward}
		{:else}
			{propNext}
		{/if}
	</svelte:element>
{/if}
<!---->
<!-- FAST FORWARD -->
{#if derivedShortMode}
	{#if propActivePage === propNumberOfPages}
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};${propDisabledStyle};cursor:not-allowed;`}
			class={`${propRest.class ?? ''} ${propDisabledClass}`}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconFastForward}
				</svelte:element>
			{:else}
				<!-- eslint-disable-next-line svelte/no-at-html-tags -->
				{@html iconFastForward}
			{/if}
		</svelte:element>
	{:else}
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<svelte:element
			this={propTag}
			style={`${propRest.style ?? ''};cursor:pointer`}
			class={`${propRest.class ?? ''}`}
			onclick={() => {
				propActivePage = propNumberOfPages;
			}}
		>
			{#if propInnerTag}
				<svelte:element this={propInnerTag} style={propInnerStyle} class={propInnerClass}>
					<!-- eslint-disable-next-line svelte/no-at-html-tags -->
					{@html iconFastForward}
				</svelte:element>
			{:else}
				<!-- eslint-disable-next-line svelte/no-at-html-tags -->
				{@html iconFastForward}
			{/if}
		</svelte:element>
	{/if}
{/if}
<!---->
