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
		<img style="height: 900px;" src='/src/lib/assets/workshop_1.png' alt="Welcome" />

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<video width="1920" height="1080" autoplay controls>
			<track default kind="captions" srclang="en" src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" />
			<source src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" type="video/mp4" />
			Your browser does not support the video tag.
		</video>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-4xl font-bold drop-shadow-sm">Module 201</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="text-base font-bold drop-shadow-sm">Unimatrix shared wallets</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- SLT -->
		<p class="text-4xl font-bold drop-shadow-sm">Learning Targets</p>
		<p>&zwnj;</p>


		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				201.1 I know what a Worspace is
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				202.2 I know how to create a workspace with a couple child addresses
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				202.3 I know how to create a workspace with a multisig wallet address
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				202.4 I can sign and send a transaction from my multisig wallet and Unimatrix
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				202.5 I understand how to use Unimatrix for a DAO website
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				Assignment 202: Build a simple DAO website
			</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- 202.1  -->
		<p class="text-4xl font-bold drop-shadow-sm">202.1</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">What is a workspace</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-4xl font-bold drop-shadow-sm">Accounts with addresses</p>
		<p>&zwnj;</p>
		<img bind:this={image} style="height: 900px;" src='/src/lib/assets/address_BIP_32.svg' alt="GC workshop" />
	</Slide>


	<Slide class="h-full place-content-center place-items-center"> <!-- TX Advanced -->
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


</Presentation>
