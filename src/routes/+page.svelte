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
	import Playground_1 from '/src/lib/assets/workshop_1.png'
	import DSL_1 from '/src/lib/assets/workshop_3.png'
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
		<img style="height: 900px;" src='/src/lib/assets/workshop_2.png' alt="Developers" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-4xl font-bold drop-shadow-sm">Module 101</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="text-base font-bold drop-shadow-sm">Getting a wallet</p>
		</Transition>
	</Slide>


	<Slide class="h-full place-content-center place-items-center"> <!-- Discord  -->
		<p class="text-4xl font-bold drop-shadow-sm">GC Discord</p>
		<p>&zwnj;</p>
		<img style="height: 400px;" src='/src/lib/assets/GC_Discord.svg' alt="GC svg" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Get wakket  -->
		<p class="text-4xl font-bold drop-shadow-sm">Get your GC wallet</p>
		<p>&zwnj;</p>
		<img style="height: 400px;" src='/src/lib/assets/Gamechanger.svg' alt="GC svg" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Airdrop  -->
		<p class="text-4xl font-bold drop-shadow-sm">Testnet Airdrop</p>
		<p>&zwnj;</p>
		<img style="height: 800px;" src='/src/lib/assets/airdrop.png' alt="Airdrop" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- POS -->
		<p class="text-4xl font-bold drop-shadow-sm">Point of sale dApp</p>
		<p>&zwnj;</p>
		<img style="height: 700px;" src='/src/lib/assets/paypad-qr.svg' alt="Tx" />
		<p>&zwnj;</p>
		<div >
			<a class="large" id="txLink" 
			href='https://www.m2tec.nl'>
			M2tec
		 </a> 
		</div>
	</Slide>	

	<Slide class="h-full place-content-center place-items-center"> <!-- Module 102 -->
		<p class="text-4xl font-bold drop-shadow-sm">Module 102</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="text-base font-bold drop-shadow-sm">Connecting with wallets</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- SLT -->
		<p class="text-4xl font-bold drop-shadow-sm">Learning Targets</p>
		<p>&zwnj;</p>


		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.1 I can analyze what is going on during a GC connection
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.2 I understand the GC script structure.
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				102.3 I can setup my developer environment.
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
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- 102.1  -->
		<p class="text-4xl font-bold drop-shadow-sm">102.1</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Under the hood</p>
		</Transition>
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

	<Slide class="h-full place-content-center place-items-center"> <!-- Playground -->
		<p class="text-4xl font-bold drop-shadow-sm">Edit in playground</p>
		<p>&zwnj;</p>
		<img style="height: 800px;" src='/src/lib/assets/open_playground.png' alt="open playground" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- 102.2  -->
		<p class="text-4xl font-bold drop-shadow-sm">102.2</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Script structure</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- DSL  -->
		<img bind:this={image3} style="height: 900px;" src={DSL_1} alt="GC workshop" />
		<Transition do={() => (image3.src = '/src/lib/assets/workshop_4.png')}></Transition>
		<Transition do={() => (image3.src = '/src/lib/assets/workshop_5.png')}></Transition>
		<Transition do={() => (image3.src = '/src/lib/assets/workshop_6.png')}></Transition>
		<Transition do={() => (image3.src = '/src/lib/assets/workshop_7.png')}></Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: Transaction steps  -->
		<div id="code">
			<Code
				bind:this={code6}
				lang="json"
				theme="github-dark"
				code={``}
			/>

			<Action
			do={() =>
				code6.update`
			{
				"type": "script",
				"title": "Pay me 1 tADA",
				"run": {...
				}
			}`}
		/>

			<Action do={() => code6.selectLines`2`} />
			<Action do={() => code6.selectLines`3`} />
			<Action do={() => code6.selectLines`4-5`} />

			<Action
				do={() =>
					code6.update`
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

			<Action do={() => code6.selectLines`0`} />

			<Action
				do={() =>
					code6.update`
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
					code6.update`
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
					code6.update`
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
				code6.update`
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
					code6.update`
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

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-4xl font-bold drop-shadow-sm">102.3</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Developer environment</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src="/src/lib/assets/code-liveserver.png" alt="GC Playground" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src="/src/lib/assets/code-run-page.png" alt="GC Playground" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Section: 102.4  -->
		<p class="text-4xl font-bold drop-shadow-sm">102.4</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">GC Library</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Image: dApp basic-->
		<img style="height: 900px;" src="/src/lib/assets/connect_link.png" alt="dApp basic" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp link only-->
		<div class="flex flex-col">
			<div id="code">
				<Code
					bind:this={code7}
					lang="html"
					theme="github-dark"
					code={`index.html:

<!DOCTYPE html>
<html>
<head>...</head>

<body class="p-3">
    <h1>dApp</h1>
    <p>This is my first dApp.</p>

    <a id="txLink" 
href='https://beta-preprod-wallet.gamechanger.finance/api/2/run/1-H
2Uz2rbQBDGX2XQxS2kjv-kCfbNJNDmEgx16aEEMdaOrHWlXXl3ZEs2hj5HL33FPkJnJ
nmpbYOab3f3NN7M6RNyUFE0jnzhdcnQVseY8BH79_PEd5thAQTAEnj3MRFTU5WlrJGW
....
OOY18tC82XUFvxj7Ctwpf6Gjr4Cum1K4HljHITd_c_lgGQ6fcvMApMXPsOCFf9r0tFn
AXlNNs_PBQAA'>
       Transaction
    </a>

    <script src="index.js"></script>
</body>
</html>`}
				/>
			</div>

		 <div >
			<a class="large" id="txLink" 
			href='https://beta-preprod-wallet.gamechanger.finance/api/2/run/1-H4sIAAAAAAAAA-2Uz2rbQBDGX2XQxS2kjv-kCfbNJNDmEgx16aEEMdaOrHWlXXl3ZEs2hj5HL33FPkJnJRsCqaGnnmpbYOab3f3NN7M6RNyUFE0jnzhdcnQVseY8BH79_PEd5thAQTAEnj3MRFTU5WlrJGWRaQ_yQyixKcgwONpU5LkPD7Sl3JbkwFgmP4VFRtCzFZcV-x6ULmjcgE2Bg7KsdK4WdQ9m80dIK5OEIwDz3O48NLYCtqAo1YagqHLW79B7YmCHxmOXfNq8D48G7tEpNBbaLAF0dFqtYNkEXpvrpHlUgCY8Xd4TFnQFqXVttbAjqLygocIeaANLyxkk6EmOmMEHSb7P0KykxC_CKTAPWJZSeGH7kDGXfnp9vZKspMvqy_FoEroWG6kureOZFw_vrTafyChtVmGpiI64cmLvISqsCp3I0XN0FKFqo55xRcO4dSx-YUDQTs08ufm_m_-km0bC4t9n4_UqMIVFsHjRGGlDHbpzqimafj1EqJQjHyYg_IvFVR5uXD64qybeK1Y73meOB3vn3N2koXWdpdvCF2uerOtNg_vBNy5vG1Xlm4xv3WR_k6vBuvBjHCd3q93N-2o82mbJKGVVjtJbt9nuB6P1TlA6E1uGs28tBJ61p66cLrKp0MgMNRIYDtpPdHyWr4xjO4ejOBR9YQyDtKj9yaI5MlMY7OjTRZ8UMeqc1Jxcob2XoJCmmHsKHgbq6LAiftNLMMmof-kq9Ln-SHXv7TF6PoOOY18tC82XUFvxj7Ctwpf6Gjr4Cum1K4HljHITd_c_lgGQ6fcvMApMXPsOCFf9r0tFn7X7H4-_AXlNNs_PBQAA'>
			Transaction
		 </a> 
		</div>
		</div>
		<Action do={() => code7.selectLines`11-18`} />
	</Slide> 

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<div class="flex flex-row">
			<div id="code">
				<Code
					bind:this={code2}
					lang="html"
					theme="github-dark"
					code={`index.html:

<!DOCTYPE html>
<html>

<head>
	<link rel="icon" type="image/png" href="/favicon.png">
	<script 
		src='https:.../npm/@gamechanger-finance/gc/dist/browser.min.js'>
	</script>
</head>

<body>
	<h1>dApp</h1>
	<p>This is my first dApp.</p>

	<script src="index.js"></script>
</body>

</html>`}
				/>
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`index.js:

async function main() {
    const gc = window.gc

    console.log(gc);
}

window.onload = function () {
    main();
}`}
				/>
				<Action do={() => code2.selectLines`9,18`} />
				<Action do={() => code3.selectLines`4`} />
			</div>
		</div>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Image: dApp basic-->
		<img style="height: 900px;" src="/src/lib/assets/dapp-basic-1.png" alt="dApp basic" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 2 -->
		<div class="flex flex-row">
			<div id="code">
				<Code
					bind:this={code4}
					lang="html"
					theme="github-dark"
					code={`index.html:

<!DOCTYPE html>
<html>

<head>
...
</head>

<body class="p-3">

    <h1>dApp</h1>
    <p>This is my first dApp.</p>

    <a id="txLink" 
       href='https://beta-preprod-wallet.gamechanger.finance'>
       Transaction
    </a>

    <script src="index.js"></script>
</body>

</html>`}
				/>
			</div>
			<div id="code">
				<Code
					bind:this={code5}
					lang="javascript"
					theme="github-dark"
					code={`index.js:

let txLinkElement = document.getElementById('txLink');

async function main() {
    const gc = window.gc

    let gcscript = {
        "type": "script",
        "title": "🚀 TX",
        "run": {...
        }
    }

    const actionUrl = await gc.encode.url({
        input: JSON.stringify(gcscript),
        apiVersion: '2',
        network: "preprod"
    })

    txLinkElement.setAttribute("href", actionUrl)
}

window.onload = function () {...}`}
				/>
			</div>
		</div>
		<Action do={() => code4.selectLines`15-18`} />

		<Action do={() => code5.selectLines`3`} />
		<Action do={() => code5.selectLines`8-13`} />
		<Action do={() => code5.selectLines`15-20`} />
		<Action do={() => code5.selectLines`21`} />
	</Slide> 

	<Slide class="h-full place-content-center place-items-center"> <!-- POS -->
		<p class="text-4xl font-bold drop-shadow-sm">Links</p>
		<div >
			<a class="large" id="txLink" 
				href='https://www.m2tec.nl'>
				M2tec website
			</a> 
		</div>
		<div >
			<a class="large" id="txLink" 
				href='https://github.com/GameChangerFinance/gamechanger.wallet/blob/main/docs/README.md'>
				GC Developer documentation
			</a> 
		</div>
		<div >
			<a class="large" id="txLink" 
				href='https://beta-wallet.gamechanger.finance/doc/api/v2'>
				GCScript and ISL Language Reference
			</a> 
		</div>
		<div >
			<a class="large" id="txLink" 
				href='https://github.com/GameChangerFinance/gamechanger.wallet/blob/main/examples/README.md'>
				GCScript 75+ code examples
			</a> 
		</div>
		<div >
			<a class="large" id="txLink" 
				href='https://www.npmjs.com/package/@gamechanger-finance/gc'>
				GC library (NPM) 
			</a> 
		</div>
		<div >
			<a class="large" id="txLink" 
				href='https://gamechanger.finance'>
				GC Wallet website 
			</a> 
		</div>
	</Slide>

</Presentation>
