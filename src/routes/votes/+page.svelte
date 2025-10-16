<script>
	let arr = [
		// 🎸 1980s
		{
			artist: 'Michael Jackson',
			name: 'Billie Jean',
			src: 'https://www.youtube.com/embed/Zi_XLOBDo_Y?si=Zt1FPG8Q9QKX3FJg',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Nirvana',
			name: 'Smells Like Teen Spirit',
			src: 'https://www.youtube.com/embed/hTWKbfoikeg?si=2azDHQiaIG7kSB6y',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Oasis',
			name: 'Wonderwall',
			src: 'https://www.youtube.com/embed/bx1Bh8ZvH84?si=7D5xZyN3GtxGrxkF',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Queen',
			name: 'Another One Bites the Dust',
			src: 'https://www.youtube.com/embed/rY0WxgSXdEE?si=9wGZ4tzcQW6EDw9_',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Bon Jovi',
			name: 'Livin’ on a Prayer',
			src: 'https://www.youtube.com/embed/lDK9QqIzhwk?si=6llbNQzJ6ZLkWQFM',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'A-ha',
			name: 'Take On Me',
			src: 'https://www.youtube.com/embed/djV11Xbc914?si=hWJtIl0OfV8Tg2KJ',
			liked: false,
			era: '1980s'
		},
		{
			artist: 'Cyndi Lauper',
			name: 'Girls Just Want to Have Fun',
			src: 'https://www.youtube.com/embed/PIb6AZdTr-A?si=mdP-9u9LwWZcvBGW',
			liked: false,
			era: '1980s'
		},

		// 🎶 1990s

		{
			artist: 'Backstreet Boys',
			name: 'I Want It That Way',
			src: 'https://www.youtube.com/embed/4fndeDfaWCg?si=4odxE0It7sRzyzC4',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Spice Girls',
			name: 'Wannabe',
			src: 'https://www.youtube.com/embed/gJLIiF15wjQ?si=3W2e7jLPx1OOPZgr',
			liked: false,
			era: '1990s'
		},
		{
			artist: 'Red Hot Chili Peppers',
			name: 'Californication',
			src: 'https://www.youtube.com/embed/YlUKcNNmywk?si=KmgH1IRmZjEjEY0o',
			liked: false,
			era: '1990s'
		}
	];
</script>

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
					class:btn-success={v.liked}
					class:btn-primary={!v.liked}
					onclick={() => (v.liked = !v.liked)}
				>
					{v.liked ? 'LIKED' : 'LIKE'}
				</button>
			</div>
		</div>
	{/each}
</div>
