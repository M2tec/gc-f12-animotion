<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'
	import Layout from './layout.svelte'

	let text: HTMLParagraphElement
	let code: Code
	let circle = tween({ x: 0, y: 80, r: 80, fill: '#00ffff' })
	let items = $state([1, 2, 3, 4])
	let layout = $state('flex gap-4')

	import Arch from '$lib/assets/Gamechanger_Architecture.svg'
	import Transparancy from '$lib/assets/Transparancy.svg'
	import Decentralization from '$lib/assets/Decentralization.svg'
	import Playground from '$lib/assets/Playground.webp'
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: true }}>
	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl drop-shadow-xl">Welcome!</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Game</p>
			<p bind:this={text} class="text-lg font-bold drop-shadow-sm">changer</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">Module 1</p>
			<p>&zwnj;</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="text-base font-bold drop-shadow-sm">Introduction</p>
		</Transition>
	</Slide> 

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">STL's</p>
			<p>&zwnj;</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				101.1: I understand why Gamechanger was built
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				101.2: I can find the GC playground
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				101.3: I can write a basic GC script
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				Assignment 101: Go find GC script in a production dApp
			</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">101.1</p>
			<p>&zwnj;</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-lg font-bold drop-shadow-sm">The Gamechanger way</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Interoperablity</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Transparancy</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Decentralization</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Security</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">GC Architecture</p>
			<img style="height: 900px;" src={Arch} alt="Gamechanger Architecture" />
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Transparancy</p>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Security</p>
			<img style="height: 900px;" src={Transparancy} alt="Gamechanger Architecture" />
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Decentralization</p>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Interoperablity</p>
			<img style="height: 900px;" src={Decentralization} alt="Gamechanger Architecture" />
		</Transition>
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

	<Slide class="h-full place-content-center place-items-center">
		<Transition><img style="height: 900px;" src={Playground} alt="GC Playground" /></Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<Transition>
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">101.3</p>
			<p>&zwnj;</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-lg font-bold drop-shadow-sm">GC script basics</p>
		</Transition>
	</Slide> 

	<Slide class="h-full place-content-center place-items-center">
		<div>
			<Code
				bind:this={code}
				lang="json"
				theme="github-dark"
				code={`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {...
				}
			}`}
			/>
			<Action do={() => code.selectLines`2`} />
			<Action do={() => code.selectLines`3`} />
			<Action do={() => code.selectLines`4-5`} />

			<Action
				do={() =>
					code.update`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {
					"build_1": {...
					},
					"sign_2": {...
					},
					"submit_3": {...
					}
				}
			}`}
			/>

			<Action
				do={() =>
					code.update`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {
					"build_1": {
					"type": "buildTx",
					"name": "TX-1",
					"tx": {
						"outputs": [{
							"address": "addr_test1qrl07u9ssdtd......2ftdp2f6rqvz02jw",
							"assets": [{
								"policyId": "ada",
								"assetName": "ada",
								"quantity": "1000000"
							}]
						}]
					}
				},
				"sign_2": {...
				},
				"submit_3": {...
				}
				}
			}`}
			/>

			<Action
				do={() =>
					code.update`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {...
					"build_1": {...
					},
					"sign_2": {
						"type": "signTxs",
						"txs": [
							"{get('cache.build_1.txHex')}"
						]
					},
					"submit_3": {...
					}
				}
			}`}
			/>

			<Action
				do={() =>
					code.update`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {...
					"build_1": {...
					},
					"sign_2": {...
					},
					"submit_3": {
						"type": "submitTxs",
            			"txs": "{get('cache.sign_2')}"
					}
				}
			}`}
			/>			
		</div>
	</Slide>
</Presentation>
