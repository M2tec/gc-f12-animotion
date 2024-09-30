<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let circle = tween({ x: 0, y: 80, r: 80, fill: '#00ffff' })
	let items = $state([1, 2, 3, 4])
	let layout = $state('flex gap-4')
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: true }}>
	<Slide class="h-full place-content-center place-items-center">
		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl drop-shadow-xl">Welcome!</p>
		<p>&zwnj; </p>
		</Transition>

		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Game</p>
		<p bind:this={text} class="text-lg font-bold drop-shadow-sm">changer</p>
		</Transition>

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Module 1</p>
		<p>&zwnj; </p>
		</Transition>

		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Introduction</p>
		</Transition>

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">STL's</p>
		<p>&zwnj; </p>
		</Transition>

		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">101.1: I understand why Gamechanger was built </p>
		</Transition>

		<Transition
		do={async () => {
			text.classList.replace('text-6xl', 'text-8xl')
			await code.update``
		}}
	>
	<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">101.2: I can find the GC playground</p>
	</Transition>

	<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">101.3: I can write a basic GC script</p>
		</Transition>

		<Transition
		do={async () => {
			text.classList.replace('text-6xl', 'text-8xl')
			await code.update``
		}}
	>
	<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">Assignment 101: Go find GC script in a production dApp</p>
	</Transition>

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">101.1</p>
		<p>&zwnj; </p>
		</Transition>

		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-lg font-bold drop-shadow-sm pb-5">The Gamechanger way </p>
		</Transition>

		<Transition
			do={async () => {
				text.classList.replace('text-6xl', 'text-8xl')
				await code.update``
			}}
		>
		<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">Interoperablity</p>
		</Transition>

		<Transition
		do={async () => {
			text.classList.replace('text-6xl', 'text-8xl')
			await code.update``
		}}
	>
	<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">Transparancy</p>
	</Transition>

	<Transition
	do={async () => {
		text.classList.replace('text-6xl', 'text-8xl')
		await code.update``
	}}
>
<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">Decentralization</p>
</Transition>

<Transition
do={async () => {
	text.classList.replace('text-6xl', 'text-8xl')
	await code.update``
}}
>
<p bind:this={text} class="text-base font-bold drop-shadow-sm pb-5">Security</p>
</Transition>
	</Slide>

</Presentation>
