<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let image: HTMLImageElement
	let image2: HTMLImageElement
	let image3: HTMLImageElement

	let code2: Code
	let code3: Code

	let code4: Code
	let code5: Code
	let code6: Code
	let code7: Code
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: false }}>
	<Slide class="h-full place-content-center place-items-center">
		<img bind:this={image} style="height: 900px;" src=/assets/workshop_1.png alt="GC workshop" />
	</Slide>
 
	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src='/assets/workshop_1.png' alt="Welcome" />

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<video width="1920" height="1080" autoplay controls>
			<track default kind="captions" srclang="en" src="/assets/GC_Intro_Edu_Gray.mp4" />
			<source src="$lib/assets/GC_Intro_Edu_Gray.mp4" type="video/mp4" />
			Your browser does not support the video tag.
		</video>
	</Slide>
<!--
	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src='$lib/assets/workshop_2.png' alt="Developers" />
	</Slide> -->


</Presentation>
