<script context="module">
	export const prerender = true;
</script>

<script>
	/**
	 * @type {FileList | null | undefined}
	 */
	let files;

	$: if (files) {
		// Note that `files` is of type `FileList`, not an Array:
		// https://developer.mozilla.org/en-US/docs/Web/API/FileList
		console.log(files);

		for (const file of files) {
			console.log(`${file.name}: ${file.size} bytes`);
		}
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>Rudi - The Running Dinner Planning Tool</h1>
	<input accept="*.csv" bind:files id="avatar" name="avatar" type="file" />
	<table>
		<thead>
			<th>Teamname</th>
			<th>E-Mail Adresse</th>
			<th>Postalische Adresse</th>
			<th>Essbesonderheiten</th>
			<th>Handynummer</th>
		</thead>
		<tbody>
			<tr>
				<td>test</td>
			</tr>
			<tr><td>test</td></tr>
		</tbody>
	</table>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	table {
		width: 100%;
		/* border: 1px solid; */
		border-collapse: collapse;
		text-align: center;
		vertical-align: middle;
	}
	thead {
		background-color: #333;
		color: white;
	}
	th,
	td {
		border: 1px solid black;
		padding: 8px;
	}
	tbody tr:nth-child(odd) {
		background-color: #fff;
	}

	tbody tr:nth-child(even) {
		background-color: #eee;
	}
</style>
