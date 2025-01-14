<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let code: Code
	let code2: Code
	let code3: Code
	let image: HTMLImageElement
	let circle = tween({ x: 0, y: 80, r: 80, fill: '#00ffff' })
	let items = $state([1, 2, 3, 4])
	let layout = $state('flex gap-4')

	import Arch from '$lib/assets/Gamechanger_Architecture_1.svg'
	import Transparancy from '$lib/assets/Transparancy.svg'
	import Decentralization from '$lib/assets/Decentralization.svg'
	import Playground from '$lib/assets/Playground.webp'
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: false }}>

	<!-- <Slide class="h-full place-content-center place-items-center">
		<video width="1920" height="1080" autoplay controls>
			<track default kind="captions" srclang="en" src='/assets/GC_Intro_Edu_Gray.mp4' />
			<source src='/assets/GC_Intro_Edu_Gray.mp4' type="video/mp4" />
			Your browser does not support the video tag.
		</video>
	</Slide> -->

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1000px;" src='/assets/workshop_1.svg' alt="Developers" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">Module 101</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="text-base font-bold drop-shadow-sm">Introduction</p>
		</Transition>
	</Slide> 

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">STL's</p>
			<p>&zwnj;</p>

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
			<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">101.1</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="pb-5 text-3xl font-bold drop-shadow-sm">The Gamechanger way</p>
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
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">GC Architecture</p>
			<img bind:this={image} style="height: 900px;" src={Arch} alt="Gamechanger Architecture" />
			<Transition do={() => (image.src = '/src/lib/assets/Gamechanger_Architecture_2.svg')}></Transition>
			<Transition do={() => (image.src = '/src/lib/assets/Gamechanger_Architecture_3.svg')}></Transition>				
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Transparancy</p>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Security</p>
			<img style="height: 900px;" src={Transparancy} alt="Gamechanger Architecture" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Decentralization</p>
			<p bind:this={text} class="pb-5 text-base font-bold drop-shadow-sm">• Interoperablity</p>
			<img style="height: 900px;" src={Decentralization} alt="Gamechanger Architecture" />	
	</Slide>


	<Slide class="h-full place-content-center place-items-center">

			<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">101.2</p>
			<p>&zwnj;</p>


		<Transition>
			<p bind:this={text} class="pb-5 text-3xl font-bold drop-shadow-sm">Playground</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src={Playground} alt="GC Playground" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
			<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">101.3</p>
			<p>&zwnj;</p>

		<Transition>
			<p bind:this={text} class="pb-5 text-3xl font-bold drop-shadow-sm">GC script basics</p>
		</Transition>
	</Slide> 


	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm mb-5">GCScript DSL</p>

		<div class="flex flex-row">
			<div class="text-column mr-5">
				Communication to the Gamechagner Wallet is done through scripts. 
				And is coded in a JSON based programming language, a language full of native Cardano-related functions.
			<br />			<br />
				This domain specific language is called GCSciprt DSL
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`
					A simple "Hello World" example in GCScript"
					
					{
    "type": "script",
    "title": "Example",
    "description": "Once executed will return 'Hello World!' ",
    "exportAs": "myResults",
    "run": {
        "myVariable": {
            "type": "data",
            "value": "Hello World"
        }
    }
}


and the isomorphic results:

{
    "exports": {
        "myResults": {
            "myVariable": "Hello World!"
        }
    }
}`}
				/>
			</div>
		</div>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm mb-5">Function calls</p>

		<div class="flex flex-row">
			<div class="text-column mr-5">
				A function call is a JSON object with a "type" property. It's value is the name of the function. 
				All the other properties are arguments.
				<br /><br />
				There is limited set of function you can call (around 40)
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`
					Example of a function call without arguments:
					{
						"type": "getCurrentAddress"
					}

					the "getCurrentAddress" function returns current wallet 
					address and has no arguments.


					Example of a function call with an argument named "value":
					{
						"type": "data",
						"value": [
							"foo",
							"bar",
							true,
							null,
							{"nested": {"object":{"inside": "here"}}}
						]
					}

					The "data function returns the JSON type passed as a "value" 
					argument, and allows you to define a constant"

					`}
				/>
			</div>
		</div>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm mb-5">Blocks of code</p>

		<div class="flex flex-row">
			<div class="text-column mr-5">
				GCScipt has nested function calls. A block of code is definded by the "script" function, 
				The body is a key-value map, or list, of function calls. They are passed on the "run" argument
				<br /><br />
				JSON arguments can be passed into block context through the "args" property 
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`
					Example of a block of code:
					{
						"type": "script",
						"run": {
							"resulte01": {"type": "data", "value": "A"},
							"resulte02": {"type": "data", "value": "B"},
							"resulte03": {"type": "data", "value": "C"}
						}
					}

					Example of a block of code passing an argument to it's context
					{
						"type": "script",
						"args": "Hey, I'm an argument!",
						"run": {
							"name":    {"type": "getname"},
							"address": {"type": "getCurrentAddress"},
							"slot":    {"type": "getCurrentSlot"}
						}
					}

					`}
				/>
			</div>
		</div>
	</Slide>


	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm mb-5">Cache and Exports</p>

		<div class="flex flex-row">
			<div class="text-column mr-5">
				Locally, a block of code, (and descendants) has a cache, a local scope memory space where child 
				function calls store their results. 
				<br /><br />
				In order to return data from script execution back to a dapp, data needs to be exported from the local cache 
				into the unique global export object. This can be done by passing an exportAs property with a name for 
				those exports, like this:
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`Example of a block of code with exports:
{
	"type": "script",
	"exportAs": "myFirstExport",
	"run": {
		"resulte01": {"type": "data", "value": "A"},
		"resulte02": {"type": "data", "value": "B"},
		"resulte03": {"type": "data", "value": "C"}
	}
}

Example of a block of code passing an argument to it's context
{
	"exports": {
		"myFirstExport": {
			"resulte01": {"A"},
			"resulte02": {"B"},
			"resulte03": {"C"}
		}
	}
}`}/>
			</div>
		</div>
	</Slide>

	<Slide class="h-full place-content-center place-items-center"> <!-- Code: dApp full 1 -->
		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm mb-5">Inline Scripting Language (ISL)</p>

		<div class="flex flex-row">
			<div class="text-column mr-5">
				ISL is a limited subset of Javascript. You can run a script inside the "macro" type function call. 
				<br /><br />
				The ISL "get" function allows you to return the value of a "block argument" of previous function 
				results stored in the script cache. 
			</div>
			<div id="code">
				<Code
					bind:this={code3}
					lang="javascript"
					theme="github-dark"
					code={`Example of a block of code with exports:
{
	"type": "script",
	"exportAs": "myPrivateWalletData",
	"return" {
			"mode": "last"
	},
	"run": {
		"address": {"type": "getCurrentAddress"},
		"hash":    {
			"type": "macro"},
			"run": {"sha512(get('cache.address'))"}
	}
}

Returns the following results
{
	"exports": {
		"myPrivateWalletData": "77688725....725048ea"
		}
	}
}`}/>
			</div>
		</div>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">

		<p bind:this={text} class="text-4xl font-bold drop-shadow-sm">101.4</p>
		<p>&zwnj;</p>


	<Transition>
		<p bind:this={text} class="pb-5 text-3xl font-bold drop-shadow-sm">A basic transaction</p>
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
