<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let circle = tween({ x: 0, y: 80, r: 80, fill: '#00ffff' })
	let items = $state([1, 2, 3, 4])
	let layout = $state('flex gap-4')

	import Arch from '$lib/assets/Gamechanger_Architecture.svg'
	import Transparancy from '$lib/assets/Transparancy.svg'
	import Decentralization from '$lib/assets/Decentralization.svg'
	import Playground_1 from '$lib/assets/playground_1.webp'
	import Playground_2 from '$lib/assets/playground_2.webp'
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: true }}>
	<Slide class="h-full place-content-center place-items-center">
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

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">STL's</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				102.1 I can send a transaction using a  GC script
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				102.2 I can analyze what is going on during a GC transaction
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				102.4 I am able to run my own scripts using GC lib
			</p>
		</Transition>

		<Transition>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">
				Assignment 102: Fork and hack payments.m2tec.nl
			</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-3xl font-bold drop-shadow-sm">102.1</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="pb-5 text-lg font-bold drop-shadow-sm">Sending transactions</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src={Playground_1} alt="GC Playground" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src={Playground_2} alt="GC Playground" />
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
				code={``}
			/>

			<Action
			do={() =>
				code.update`
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

			<Action do={() => code.selectLines`0`} />

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
