<script>
	let arr = [
		// 🎸 1980s
		{
			artist: 'Whitney Houston',
			name: 'I Wanna Dance with Somebody',
			src: 'https://www.youtube.com/embed/eH3giaIzONA',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Prince',
			name: 'Purple Rain',
			src: 'https://www.youtube.com/embed/TvnYmWpD_T8',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Madonna',
			name: 'Like a Prayer',
			src: 'https://www.youtube.com/embed/79fzeNUqQbQ',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'TLC',
			name: 'No Scrubs',
			src: 'https://www.youtube.com/embed/FrLequ6dUdM',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'George Michael',
			name: 'Faith',
			src: 'https://www.youtube.com/embed/6Cs3Pvmmv0E',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Radiohead',
			name: 'Creep',
			src: 'https://www.youtube.com/embed/XFkzRNyygfk',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Phil Collins',
			name: 'In the Air Tonight',
			src: 'https://www.youtube.com/embed/YkADj0TPrJA',
			liked: false,
			era: '1980s'
		},

		// 🎶 1990s

		{
			artist: 'The Police',
			name: 'Every Breath You Take',
			src: 'https://www.youtube.com/embed/OMOGaugKpzs',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Michael Jackson',
			name: 'Smooth Criminal',
			src: 'https://www.youtube.com/embed/h_D3VFfhvs4',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Coolio',
			name: "Gangsta's Paradise",
			src: 'https://www.youtube.com/embed/fPO76Jlnz6c',
			liked: false,
			era: '1990s'
		}
	];
</script>

<h1 class="mb-5">
	You can vote any songs that you want to have in the home page by clicking thumbs up or thumbs
	down.
</h1>

<div class="grid grid-cols-2 gap-2">
	{#each arr as v, i}
		<div class="rounded-lg bg-base-300 p-2">
			<div
				class="badge"
				class:badge-info={v.era === '1980s'}
				class:badge-success={v.era === '1990s'}
			>
				{v.era}..
			</div>
			<div>{v.artist}</div>
			<div>{v.name.substr(0, 20)}...</div>
			<iframe
				width="100%"
				height="120"
				src={v.src}
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
				referrerpolicy="strict-origin-when-cross-origin"
				allowfullscreen
			></iframe>
			<div class="mt-1 flex justify-end">
				<button
					class="btn btn-sm"
					class:btn-success={v.thumbsDown}
					class:btn-primary={!v.thumbsDown}
					onclick={() => (v.thumbsDown = !v.thumbsDown)}
				>
					{v.thumbsDown ? 'thumbs up!' : 'thumbs up?'}
				</button>
				<button
					class="btn btn-sm"
					class:btn-success={v.loved}
					class:btn-primary={!v.loved}
					onclick={() => (v.loved = !v.loved)}
				>
					{v.loved ? 'thumbs down!' : 'thumbs down?'}
				</button>
			</div>
		</div>
	{/each}
</div>
