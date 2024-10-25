<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let image: HTMLImageElement
	let image2: HTMLImageElement

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
	<!-- 
	<Slide class="h-full place-content-center place-items-center">
		<p class="text-3xl font-bold drop-shadow-sm">102.1</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-lg font-bold drop-shadow-sm">Sending transactions</p>
		</Transition> 
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

-->
	<Slide class="h-full place-content-center place-items-center">
		<div class="flex flex-row">
			<div id="code">
				<Code
					bind:this={code}
					lang="json"
					theme="github-dark"
					code={`
		{
			"type": "script",
			"title": "Pay me 1 tADA",
			"description": 
					"This is a payment request. Developer notes: The 'outputs' 
					property of the 'buildTx' API function allows you to define 
					multi-asset transaction outputs. In Cardano assets are 
					defined by a policyId and an assetName, for tADA we use 
					'ada' in both cases. A GameChanger Wallet Dapp Demo. 
					https://gamechanger.finance/",
			"run": {...
			}
		}`}
				/>
			</div>
			<img
				bind:this={image2}
				style="height: 950px;"
				src="/src/lib/assets/advanced_1.webp"
				alt="GC Playground"
			/>
		</div>

		<Action do={() => code.selectLines`3`} />
		<Action do={() => (image2.src = '/src/lib/assets/advanced_2.webp')} />

		<Action do={() => code.selectLines`4-10`} />
		<Action do={() => (image2.src = '/src/lib/assets/advanced_3.webp')} />

		<Action do={() => (image2.src = '/src/lib/assets/advanced_4.webp')} />
		<Action do={() => (image2.src = '/src/lib/assets/advanced_5a.webp')} />
		<Action do={() => (image2.src = '/src/lib/assets/advanced_6a.webp')} />

		<Action
			do={async () => {
				await code.update`
		{
			"type": "script",
			"title": "Pay me 1 tADA",
			"description": "This....",
			"run": {...
			}
		}`
				await code.selectLines`5`
			}}
		/>					
			
		<Action
			do={async () => {
				await code.update`
		{
			"type": "script",
			"title": "Pay me 1 tADA",
			"description": "This....",
			"run": {
				"stage1_build_transaction": {
					"type": "buildTx",
					"tx": {
						"outputs": [
							{
								"address": "addr_test1qrl...ftdp2f6rqvz02jw",
								"assets": [
									{
										"policyId": "ada",
										"assetName": "ada",
										"quantity": "1000000"
									}
								]
							}
						]
					}
				},
				"stage2_sign_transaction": {...
				},....
			`
				await code.selectLines`6`
			}}
		/>			

		<Action do={() => (image2.src = '/src/lib/assets/advanced_7a.webp')} />			

		<Action
			do={async () => {
				await code.update`
		{
			"type": "script",
			"title": "Pay me 1 tADA",
			"description": "This....",
			"run": {
				"stage1_build_transaction": {...
				},
       			"stage2_sign_transaction": {
					"type": "signTxs",
					"namePattern": "Signed Demo Transaction",
					"detailedPermissions": false,
					"txs": [
						"{get('cache.stage1_build_transaction.txHex')}"
					]
				}...
        				`
				await code.selectLines`8,13`
			}}
		/>	


		<Action do={() => (image2.src = '/src/lib/assets/advanced_8a.webp')} />	

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
	<!-- 
	<Slide class="h-full place-content-center place-items-center">
		<div>
			<Code bind:this={code} lang="json" theme="github-dark" code={``} />

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
	</Slide> -->
</Presentation>
