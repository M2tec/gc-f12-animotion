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
            201.2 I know how to create a workspace with child addresses
        </p>
    </Transition>

    <Transition>
        <p class="pb-5 text-base font-bold drop-shadow-sm">
            201.3 I know how to create a workspace with a multisig wallet address
        </p>
    </Transition>

    <Transition>
        <p class="pb-5 text-base font-bold drop-shadow-sm">
            Assignment 201: Build a simple DAO website
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

<Slide class="h-full place-content-center place-items-center"> <!-- Indexes  -->
    <p class="text-4xl font-bold drop-shadow-sm">Accounts with addresses</p>
    <p>&zwnj;</p>
    <img bind:this={image} style="height: 900px;" src='/src/lib/assets/address_BIP_32.svg' alt="GC workshop" />
</Slide>

<Slide class="h-full place-content-center place-items-center"> <!-- Workspace -->
    <p class="text-4xl font-bold drop-shadow-sm">Workspace script</p>
    <p>&zwnj;</p>	
    <div class="flex flex-row gap-8">


        <div id="code">
            <Code
                bind:this={code}
                lang="json"
                theme="github-dark"
                code={`
`}
            />
        </div>
        <img 
            bind:this={image2}
            style="height: 920px;"
            src="/assets/workspace_1.png"
            alt="GC Playground"
        />
    </div>

    <Action
        do={async () => {
            await code.update`{
    "type": "script",
    "title": "Load a configuration",
    "description": "Loading a Workspace configuration into wallet",
    "run": {
        "usingWorkspaces": {
            "type": "loadConfig",
            "updateId": "Workspace-exercise-2",
            "layers": [
                { ... },
                { ... },
                { ... }
            ]
        }
    }
}`
            await code.selectLines`7`
        }}
    />

    <Action
        do={async () => {
            await code.update`{
    "type": "script",
    "title": "Load a configuration",
    "description": "Loading a Workspace configuration",
    "run": {
        "usingWorkspaces": {
        "type": "loadConfig",
        "updateId": "Workspace-exercise-2",
        "layers": [{
            "type": "Workspace",
                "items": [{
                        "namePattern": "my_workspace_2",
                        "titlePattern": "My Workspace_2",
                        "descriptionPattern": "Wallet settings!"
                }]
            }]
        }
    }
}`
            await code.selectLines`9-16`
        }}
    />

</Slide>

<Slide class="h-full place-content-center place-items-center"> <!-- 202.2  -->
    <p class="text-4xl font-bold drop-shadow-sm">202.2</p>
    <p>&zwnj;</p>

    <Transition>
        <p class="pb-5 text-base font-bold drop-shadow-sm">Adding child addresses</p>
    </Transition>
</Slide>

<Slide class="h-full place-content-center place-items-center">
    <!-- Child addreses -->
    <p class="text-4xl font-bold drop-shadow-sm">Child addresses</p>
    <p>&zwnj;</p>
    <div class="flex flex-row gap-8">
        <div id="code">
            <Code bind:this={code2} lang="json" theme="github-dark" code={``} />
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
            await code2.update`{
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
            await code2.selectLines`9-11`
        }}
    />

    <Action
        do={async () => {
            await code2.update`{
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
            await code2.selectLines`10`
        }}
    />

    <Action
        do={async () => {
            await code2.update`{
    "type": "script",
    ...
    "run": {
        "usingWorkspaces": {
            "type": "loadConfig",
            "updateId": "Workspace-exercise-1",
            "layers": [
                {
                    "type": "Workspace",
                    "items": [{ "namePattern": "my_workspace_2",
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
            await code2.selectLines`15`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`11, 17`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`20-23`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`26-29`
        }}
    />

    <Action
        do={async () => {
            await code2.update`{
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
            await code2.selectLines`11,16,26`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`19,30`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`20,31`
        }}
    />

    <Action
        do={async () => {
            await code2.selectLines`29`
        }}
    />
</Slide>

<Slide class="h-full place-content-center place-items-center"> <!-- 202.3  -->
    <p class="text-4xl font-bold drop-shadow-sm">202.3</p>
    <p>&zwnj;</p>

    <Transition>
        <p class="pb-5 text-base font-bold drop-shadow-sm">Multisigs</p>
    </Transition>
</Slide>


    <Slide class="h-full place-content-center place-items-center">
        <!-- Multisigs -->
        <p class="text-4xl font-bold drop-shadow-sm">Multisig workspace</p>
        <p>&zwnj;</p>

        <div id="code-single">
            <Code bind:this={code3} lang="json" theme="github-dark" code={``} />
        </div>

        <Action
            do={async () => {
                await code3.update`{
    "type": "script",
    "title": "Multisig 2 of 2 Workspace",
    "description": "Alice and Bob must sign",
    "args": {
        "Alice": {
            "spendKeyHashHex": "ccc8ff3028155a487228a6e0ecf02edcd3cd42a02ab4eee947766227",
            "stakeKeyHashHex": "9957781a7c45357f96120ee73f80bfaa98adae68ce6ae80a3014d175"
        },
        "Bob": {
            "spendKeyHashHex": "0146e2d57bb52dc888f15cf17fef414e4ab1b71a36fdf8cd199bc2c2",
            "stakeKeyHashHex": "80ca5adf47eb9ff0f4408bd0e3927fc39e1472d460441d4cdb9d2d28"
        }
    },
    "run": {
    ...
    }
}
`
                await code3.selectLines`6-13`
            }}
        />

        <Action
            do={async () => {
                await code3.update`{
    "type": "script",
    "title": "Multisig 2 of 2 Workspace",
    "description": "Alice and Bob must sign",
    "args":{ "Alice":{ "spendKeyHashHex": "ccc8ff3028155a487228a6e0ecf02edcd3cd42a02ab4eee947766227",
                       "stakeKeyHashHex": "9957781a7c45357f96120ee73f80bfaa98adae68ce6ae80a3014d175"},
             "Bob":  { "spendKeyHashHex": "0146e2d57bb52dc888f15cf17fef414e4ab1b71a36fdf8cd199bc2c2",
                       "stakeKeyHashHex": "80ca5adf47eb9ff0f4408bd0e3927fc39e1472d460441d4cdb9d2d28"}},
    "run": {
        "walletSetup": {
            "type": "loadConfig",
            "updateId": "multisigs_update_1",
            "layers": [
                {
                    "type": "Workspace",
                    "items": [
                        {
                            "namePattern": "multisigs",
                            "titlePattern": "Multisig Wallets",
                            "descriptionPattern": "Example multisigs involving Alice, Bob and Charles wallets"
                        }
                    ]
                },
                { "type": "NativeScript", ... },
                { "type": "Address", ... }
            ]
        }
    }
}
`
                await code3.selectLines`15-22`
            }}
        />

        <Action
            do={async () => {
                await code3.update`{
    "type": "script",
    "title": "Multisig 2 of 2 Workspace",
    "description": "Alice and Bob must sign",
    "args":{ "Alice":{ "spendKeyHashHex": "ccc8ff3028155a487228a6e0ecf02edcd3cd42a02ab4eee947766227",
                       "stakeKeyHashHex": "9957781a7c45357f96120ee73f80bfaa98adae68ce6ae80a3014d175"},
             "Bob":  { "spendKeyHashHex": "0146e2d57bb52dc888f15cf17fef414e4ab1b71a36fdf8cd199bc2c2",
                       "stakeKeyHashHex": "80ca5adf47eb9ff0f4408bd0e3927fc39e1472d460441d4cdb9d2d28"}},
    "run": {
        "walletSetup": {
            "type": "loadConfig",
            "updateId": "multisigs_update_1",
            "layers": [
                {
                    "type": "Workspace", ... }
                {
                    "type": "NativeScript",
                    "workspaceIds": [ "multisigs" ],               
                    "namePattern": "2_of_2_{key}_script",
                    "items": {
                        "spend": {
                            "all": { "alice": {	"pubKeyHashHex": "{get('args.Alice.spendKeyHashHex')}" },
                                     "bob":   { "pubKeyHashHex": "{get('args.Bob.spendKeyHashHex')}" }
                            }
                        },
                        "stake": {
                            "all": { "alice": { "pubKeyHashHex": "{get('args.Alice.stakeKeyHashHex')}" },
                                     "bob":   { "pubKeyHashHex": "{get('args.Bob.stakeKeyHashHex')}"
                                }
                            }
                        }
                    }
                },
                { "type": "Address", ... }
            ]
        }
}
`
                await code3.selectLines`17-32`
            }}
        />

        <Action
        do={async () => {
            await code3.selectLines`19`
        }}
    />


        <Action
            do={async () => {
                await code3.update`{
    "type": "script",
    "title": "Multisig 2 of 2 Workspace",
    "description": "Alice and Bob must sign",
    "args":{ "Alice":{ "spendKeyHashHex": "ccc8ff3028155a487228a6e0ecf02edcd3cd42a02ab4eee947766227",
                       "stakeKeyHashHex": "9957781a7c45357f96120ee73f80bfaa98adae68ce6ae80a3014d175"},
             "Bob":  { "spendKeyHashHex": "0146e2d57bb52dc888f15cf17fef414e4ab1b71a36fdf8cd199bc2c2",
                       "stakeKeyHashHex": "80ca5adf47eb9ff0f4408bd0e3927fc39e1472d460441d4cdb9d2d28"}},
    "run": {
    "walletSetup": {
        "type": "loadConfig",
        "updateId": "multisigs_update_1",
        "layers": [
            {
                "type": "Workspace", ... }
            {
                "type": "NativeScript",
                "workspaceIds": [ "multisigs" ],               
                "namePattern": "2_of_2_{key}_script",
                "items": { "spend": { ... },
                           "stake": { ... } }
                }
            },
            {
                "type": "Address",
                "workspaceIds": [
                    "multisigs"
                ],
                "items": [ {
                        "namePattern": "2_of_2",
                        "spendNativeScriptName": "2_of_2_spend_script",
                        "stakeNativeScriptName": "2_of_2_stake_script"
                }]
            }
        ]
}
`
                await code3.selectLines`20,21,31,32`
            }}
        />
    </Slide>



</Presentation>
