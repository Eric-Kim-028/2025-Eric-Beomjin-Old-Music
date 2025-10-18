<script>
	let arr = [
		// 🎸 1980s
		{
			artist: 'Michael Jackson',
			name: 'Billie Jean',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Nirvana',
			name: 'Smells Like Teen Spirit',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Oasis',
			name: 'Wonderwall',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Queen',
			name: 'Another One Bites the Dust',
			liked: false,
			era: '1980s'
		}
	];
</script>

<iframe
	width="100%"
	height="300"
	src={'https://www.youtube.com/embed/Zi_XLOBDo_Y?si=Zt1FPG8Q9QKX3FJg'}
	title="YouTube video player"
	frameborder="0"
	allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
	referrerpolicy="strict-origin-when-cross-origin"
	allowfullscreen
></iframe>
<div class="grid grid-cols-1 gap-2">
	{#each arr as v, i}
		<div class="flex justify-evenly rounded-lg bg-base-300 p-2">
			<div
				class="badge"
				class:badge-info={v.era === '1980s'}
				class:badge-success={v.era === '1990s'}
			>
				{v.era}..
			</div>
			<div>{v.artist}</div>
			<div>{v.name.substr(0, 1000)}</div>
			<iframe
				width="50%"
				height="1"
				src={v.src}
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
				referrerpolicy="strict-origin-when-cross-origin"
				allowfullscreen
			></iframe>
			<div class="mt-1 flex justify-start">
				<button
					class="btn btn-sm"
					class:btn-success={v.liked}
					class:btn-error={!v.liked}
					onclick={() => (v.liked = !v.liked)}
				>
					{v.liked ? 'delete' : 'delete'}
				</button>
			</div>
			<button
				class="btn btn-sm"
				class:btn-success={v.played}
				class:btn-primary={!v.played}
				onclick={() => (v.played = !v.played)}
			>
				{v.played ? 'playing' : 'play'}
			</button>
		</div>
	{/each}
</div>
