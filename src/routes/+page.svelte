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
		<img style="height: 900px;" src="/src/lib/assets/workshop_1.png" alt="Welcome" />
	</Slide>

	<!-- <Slide class="h-full place-content-center place-items-center">
		<video width="1920" height="1080" autoplay controls>
			<track default kind="captions" srclang="en" src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" />
			<source src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" type="video/mp4" />
			Your browser does not support the video tag.
		</video>
	</Slide> -->

	<Slide class="h-full place-content-center place-items-center">
		<!-- Child addreses -->
		<p class="text-4xl font-bold drop-shadow-sm">Child addresses</p>
		<p>&zwnj;</p>
		<div class="flex flex-row gap-8">
			<div id="code">
				<Code bind:this={code} lang="json" theme="github-dark" code={``} />
			</div>
			<img
				bind:this={image3}
				style="height: 920px;"
				src="/assets/workspace_address.png"
				alt="GC Playground"
			/>
		</div>

		<Action
			do={async () => {
				await code.update`
{
	"type": "script",
		...
	"run": {
		"usingWorkspaces": {
			"type": "loadConfig",
			...
			"layers": [
				{ "type": "Workspace", ... }
				{ "type": "Key", ... }
			 	{ "type": "Address", ... }
			]		
		}
	}
}`
				await code.selectLines`9-11`
			}}
		/>

		<Action
			do={async () => {
				await code.update`
{
    "type": "script",
	  ...
    "run": {
        "usingWorkspaces": {
            "type": "loadConfig",
            "updateId": "Workspace-exercise-1",
            "layers": [
                {
                    "type": "Workspace",
                    "items": [{
                    	"namePattern": "my_workspace_2",
					            ... }]
                },
								{ "type": "Key", ... }
								{ "type": "Address", ... }
            ]
        }
    }
}`
				await code.selectLines`12`
			}}
		/>

		<Action
			do={async () => {
				await code.update`
{
    "type": "script",
	  ...
    "run": {
        "usingWorkspaces": {
            "type": "loadConfig",
            "updateId": "Workspace-exercise-1",
            "layers": [
                {
                    "type": "Workspace",
                    "items": [{
                    	"namePattern": "my_workspace_2",
					            ... }]
                },
                {
                    "type": "Key",
                    "workspaceIds": [
                        "my_workspace_2"
                    ],
                    "items": [{
                            "namePattern": "my_key_spend",
                            "kind": "spend",
                            "accountIndex": 5,
                            "addressIndex": 0
                        },
                        {
                            "namePattern": "my_key_stake",
                            "kind": "stake",
                            "accountIndex": 5,
                            "addressIndex": 0
                        }]
                },
                { ... }
            ]
        }
    }
}`
				await code.selectLines`16`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`12, 18`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`21-25`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`26-31`
			}}
		/>

		<Action
			do={async () => {
				await code.update`
{
    "type": "script",
	  ...
    "run": {
        "usingWorkspaces": {
            "type": "loadConfig",
            "updateId": "Workspace-exercise-1",
            "layers": [
                {
                    "type": "Workspace",
                    "items": [{ "namePattern": "my_workspace_2",...}]
                },
                {
                    "type": "Key",
                    "workspaceIds": [
                        "my_workspace_2"
                    ],
                    "items": [
                        { "namePattern": "my_key_spend", ... },
                        { "namePattern": "my_key_stake", ... }
                    ]
                },
                {
                    "type": "Address",
                    "workspaceIds": [
                        "my_workspace_2"
                    ],
                    "items": [{
                            "namePattern": "My_Address_1",
                            "stakePubKeyName": "my_key_spend",
                            "spendPubKeyName": "my_key_stake"
                        }]
                }
            ]
        }
    }
}`
				await code.selectLines`11,16,26`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`19,30`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`20,31`
			}}
		/>

		<Action
			do={async () => {
				await code.selectLines`29`
			}}
		/>
	</Slide>
</Presentation>
