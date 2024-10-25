<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let image: HTMLImageElement

	import Playground_1 from '$lib/assets/playground_1.webp'
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: true }}>
	<!-- <Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl drop-shadow-xl">Welcome!</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Game</p>
			<p bind:this={text} class="text-lg font-bold drop-shadow-sm">changer</p>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Module 102</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="text-base font-bold drop-shadow-sm">Introduction</p>
		</Transition>
	</Slide> 
-->
	<!-- 
	<Slide class="h-full place-content-center place-items-center">
			<p class="text-3xl font-bold drop-shadow-sm">STL's</p>
			<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.1 I can send a transaction using a  GC script
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.2 I can analyze what is going on during a GC transaction
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.4 I am able to run my own scripts using GC lib
			</p>
		</Transition>
		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				Assignment 102: Fork and hack payments.m2tec.nl
			</p>
		</Transition>
	</Slide>  -->

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-3xl font-bold drop-shadow-sm">102.1</p>
		<p>&zwnj;</p>
		<!-- 
		<Transition>
			<p class="pb-5 text-lg font-bold drop-shadow-sm">Sending transactions</p>
		</Transition> -->
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img bind:this={image} style="height: 900px;" src={Playground_1} alt="GC Playground" />
		<Transition do={() => (image.src = '/src/lib/assets/playground_2.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_3.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_4.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_5.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_6.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_7.webp')}></Transition>
		<Transition do={() => (image.src = '/src/lib/assets/playground_8.webp')}></Transition>
	</Slide>

	

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">101.2</p>
			<p>&zwnj;</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-lg font-bold drop-shadow-sm">Playground</p>
		</Transition>
	</Slide>


</Presentation>
