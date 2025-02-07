<script lang="ts">
	import { Presentation, Slide, Code, Transition, Action } from '@animotion/core'
	import { tween } from '@animotion/motion'

	let text: HTMLParagraphElement
	let image: HTMLImageElement
	let image2: HTMLImageElement
	let image3: HTMLImageElement

    let code: Code
	let code2: Code
	let code3: Code
	let code4: Code
	let code5: Code
	let code6: Code
	let code7: Code
	let code8: Code
	let code9: Code
    let code10: Code
    let code11: Code
    let code12: Code
    let code13: Code
    let code14: Code
    let code15: Code
    let code16: Code
	let code17: Code
	let code18: Code
	let code19: Code
	let code20: Code
	let code21: Code
	let code22: Code
</script>

<Presentation options={{ history: true, transition: 'slide', controls: false, progress: false }}>
	<!-- <Slide class="h-full place-content-center place-items-center">
        <video width="1920" height="1080" autoplay controls>
            <track default kind="captions" srclang="en" src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" />
            <source src="/src/lib/assets/GC_Intro_Edu_Gray.mp4" type="video/mp4" />
            Your browser does not support the video tag.
        </video>
    </Slide> -->

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 900px;" src="/assets/workshop_1.svg" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<p class="text-4xl font-bold drop-shadow-sm">Module 301</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="text-base font-bold drop-shadow-sm">Unimatrix</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- SLT -->
		<p class="text-4xl font-bold drop-shadow-sm">Learning Targets</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				301.1 I can sign and send a transaction from my multisig wallet and Unimatrix
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				301.2 I know how to enable Unimatrix signing in a GCscript
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				301.3 I know how to start the Unimatrix examples
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				301.4 I know how to use the Unimatrix Vite template
			</p>
		</Transition>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">
				301.5 I know how to build a DAO site with Unimatrix
			</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- 301.1  -->
		<p class="text-4xl font-bold drop-shadow-sm">301.1</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Multisig transactions</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Adding signers -->
		<p class="text-4xl font-bold drop-shadow-sm">Adding required signers</p>
		<p>&zwnj;</p>

		<div id="code-small">
			<Code
				bind:this={code}
				lang="json"
				theme="github-dark"
				code={`
`}
			/>
		</div>

		<Action
			do={async () => {
				await code.update`{
    "type": "script",
    ...
    "run": {
        "stage1_build_transaction": {
            "type": "buildTx",
            ...
            "tx": {
                "outputs": [ ... ],
                "requiredSigners": {
                    "spend": "1c983ed55319939f6e5...acdab81d6ad4a520d3f3"
                },
                "options": {
                    "autoProvision": {
                        "workspaceNativeScript": true
                    },
                    "autoOptionalSigners": {
                        "nativeScript": true
                    }
                }
            }
        },
        "stage2_sign_transaction": { ... },
        "stage3_submit_transaction": { ... }
    }
}`
				await code.selectLines`10-20`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Wallet info -->
		<p class="text-4xl font-bold drop-shadow-sm">Get wallet information</p>
		<p>&zwnj;</p>

		<div class="flex flex-row gap-8">
			<div id="code-small">
				<Code bind:this={code4} lang="json" theme="github-dark" code={``} />
			</div>
			<img
				bind:this={image3}
				style="height: 1000px;"
				src="/assets/exports_spend_pub_key.png"
				alt="GC Playground"
			/>
		</div>

		<Action
			do={async () => {
				await code4.update`{
    "type": "script",
    "title": "Share your public key information?",
    "description": "Spending and staking public key hashes export",
    "exportAs": "data",
    "return": {
        "mode": "last"
    },
    "run": {
        "getSpendCredential": {
            "type": "getSpendingPublicKey"
        },
        "getStakeCredential": {
            "type": "getStakingPublicKey"
        },
        "finally": {
            "type": "macro",
            "run": {
                "spend": "{get('cache.getSpendCredential.pubKeyHashHex')}",
                "stake": "{get('cache.getStakeCredential.pubKeyHashHex')}"
            }
        }
    }
}`
				await code4.selectLines`11-14`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1100px;" src="/assets/multisig_confirm.png" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- 301.2  -->
		<p class="text-4xl font-bold drop-shadow-sm">301.2</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">GCscript and Unimatrix</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Unimatrix and signTxs -->
		<p class="text-4xl font-bold drop-shadow-sm">Adding Unimatrix to signTxs</p>
		<p>&zwnj;</p>
		<div class="flex flex-row gap-8">
			<div id="code-single">
				<Code bind:this={code2} lang="json" theme="github-dark" code={``} />
			</div>
		</div>

		<Action
			do={async () => {
				await code2.update`{
    "type": "script",
    "run": {
        "build1": {
            "type": "buildTx",
            "tx": { ... },
                "options": {
                    "autoProvision": {
                        "workspaceNativeScript": true
                    },
                    "autoOptionalSigners": {
                        "nativeScript": true
                    }}}},
        "sign": {
            "detailedPermissions": false,
            "type": "signTxs",
            "multisig": [
                { "kind": "CurrentWorkspace" },
                {
                    "id": "multisig_1234",
                    "kind": "Unimatrix",
                    "share": true,
                    "shareTxs": true,
                    "announceTxHashes": true,
                    "announceTxHashesSubPath": "signTxs",
                    "relays": [ "https://ar02.gamechanger.finance:2083/unimatrix/gun" ]
                }
            ],
            "txs": [ "{get('cache.build1.txHex')}" ]
        },
        "submit": { ... }
    }
}`
				await code2.selectLines`20-26`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- 301.3  -->
		<p class="text-4xl font-bold drop-shadow-sm">301.3</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Unimatrix examples</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Building examples -->
		<p class="text-4xl font-bold drop-shadow-sm">Building the examples</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 80px;">
			<Code bind:this={code3} lang="bash" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code3.update`
git clone https://github.com/GameChangerFinance/unimatrix

cd unimatrix
npm install
npm run build
npm link

cd examples/react:
npm link @gamechanger-finance/unimatrix
npm install
npm run dev
`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1100px;" src="/assets/unimatrix_run_dev.png" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1500px;" src="/assets/unimatrix_node.png" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1100px;" src="/assets/sign_unimatrix.png" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- 301.3  -->
		<p class="text-4xl font-bold drop-shadow-sm">301.4</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Unimatrix Vite template</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Setup environment -->
		<p class="text-4xl font-bold drop-shadow-sm">Setup environment</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 75px;">
			<Code bind:this={code10} lang="bash" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code10.update`
$ nvm use v18.20.4

$ npm create vite@latest gc-unimatrix-dao -- --template react
    `
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Package.json -->
		<p class="text-4xl font-bold drop-shadow-sm">Libraries and versions</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 45px;">
			<Code bind:this={code5} lang="json" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code5.update`package.json
{
	"name": "gc-unimatrix-dao",
	"private": true,
	"version": "0.0.0",
	"type": "module",
	"scripts": {
		"dev": "vite",
		"build": "vite build",
		"lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
		"preview": "vite preview",
},
	"dependencies": {
		"@emurgo/cardano-serialization-lib-browser": "^13.2.1",
		"@gamechanger-finance/gc": "^0.1.0",
		"@gamechanger-finance/unimatrix": "^1.0.3",
		"gun": "^0.2020.1240",
		"react": "^18.2.0",
		"react-dom": "^18.2.0",
		"react-router-dom": "^6.28.2"
	},
	"devDependencies": {
		"@types/react": "^18.2.66",
		"@types/react-dom": "^18.2.22",
		"@vitejs/plugin-react": "^4.2.1",
		"eslint": "^8.57.0",
		"eslint-plugin-react": "^7.34.1",
		"eslint-plugin-react-hooks": "^4.6.0",
		"eslint-plugin-react-refresh": "^0.4.6",
		"vite": "^5.2.0",
		"vite-plugin-node-polyfills": "0.17.0",
		"vite-plugin-top-level-await": "^1.4.1",
		"vite-plugin-wasm": "^3.3.0"
	}
}`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- vite.config.js -->
		<p class="text-4xl font-bold drop-shadow-sm">Vite configuration</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 42px;">
			<Code bind:this={code6} lang="javascript" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code6.update`vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import wasm from "vite-plugin-wasm";
import topLevelAwait from "vite-plugin-top-level-await";
import { nodePolyfills } from 'vite-plugin-node-polyfills'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [
    nodePolyfills({
      include: ['crypto'] ,
      globals:{
        Buffer: true,
        global: true,
      }
    }),
    wasm(),
    topLevelAwait(),
    react()
  ],
  optimizeDeps: {
    esbuildOptions: {
        external: ['*.ttf'],
    },
    rollupOptions: {
      // Exclude files with the *.cy.tsx extension from being processed by Vite
      external: [
        "*.ttf",
        "*/vite-plugin-node-polyfills/*"
      ],
    }
  },
  exclude: ['*.ttf'],
})`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- npm install -->
		<p class="text-4xl font-bold drop-shadow-sm">Install libraries</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 42px;">
			<Code bind:this={code7} lang="bash" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code7.update`
$ npm install`
			}}
		/>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Building examples -->
		<p class="text-4xl font-bold drop-shadow-sm">index.html</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 49px;">
			<Code bind:this={code8} lang="bash" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code8.update`index.html:
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DOA Unimatrix</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" 
          rel="stylesheet" 
          integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" 
          crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" 
            integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" 
            crossorigin="anonymous">
    </script>

    <script src="https://cdn.jsdelivr.net/npm/@gamechanger-finance/gc/dist/browser.min.js">
    </script>
  
    </head>
  <body>
    <div id="root"></div>
  
    <script type="module" src="/src/main.jsx"></script>
  
  </body>
</html>`
await code8.selectLines`10-17`
			}}
		/>

		<Action
			do={async () => {
				await code8.selectLines`19,20,26`

			}}
		/>


	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- HOME -->
		<p class="text-4xl font-bold drop-shadow-sm">Home</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 58px;">
			<Code bind:this={code9} lang="javascript" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code9.update`src/pages/Home.jsx:
import { useEffect, useState } from 'react'
...
const Home = () => {
  const [host, setHost] = useState("")

  const gc = window.gc;

  async function handleGC(gcscript) {

    let url = await gc.encode.url({
      input: JSON.stringify(gcscript), 
      apiVersion: '2', //APIV2
      network: 'preprod', // mainnet or preprod
      encoding: 'gzip' 
    });

    window.open(url, '_blank', 
    'location=yes,height=700,width=520,scrollbars=yes,status=yes');
  }

  useEffect(() => { ... }, []);
  async function getWalletData() { ... }
  return ( ... )
};
export default Home;
`
await code9.selectLines`6, 10-19`
			}}

		/>


		<Action
			do={async () => {
				await code9.update`src/pages/Home.jsx:
import { useEffect, useState } from 'react'
...

const Home = () => {

  const [host, setHost] = useState("")

  const gc = window.gc;
  async function handleGC(gcscript) { ... }

  useEffect(() => {
    let myHostname = location.protocol + '//' + location.host
    setHost(myHostname);
  }, []);

  async function getWalletData() { ... }

  return ( ... )
};
export default Home;
`
await code9.selectLines`7, 13, 14`
			}}
		/>

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Page routing -->
		<p class="text-4xl font-bold drop-shadow-sm">Page routing</p>
		<p>&zwnj;</p>
		<div class="flex flex-row gap-8">
		<div id="code-single" style="font-size: 69px;">
			<Code bind:this={code13} lang="javascript" theme="github-dark" code={``} />
		</div>
        <div id="code-single" style="font-size: 62px;">
			<Code bind:this={code14} lang="bash" theme="github-dark" code={``} />
		</div>
    </div>
		<Action
			do={async () => {
				await code13.update`src/App.jsx:
import './App.css'
import { Route, 
         createBrowserRouter, createRoutesFromElements, 
         RouterProvider } from 'react-router-dom';
import Home from "./pages/Home";
import Data from "./pages/Data";

const router = createBrowserRouter(
  createRoutesFromElements(
    <Route>
      <Route index element={<Home />} />
      <Route path="return-data" element={<Data />} />
    </Route>
  )
)

function App({routes}) {
  return ( <RouterProvider router={router}/> )
}
export default App
`
await code13.selectLines`3-5, 19`
await code14.update`http://localhost:5174/return-data?d=1-H4sIAAAAA...1_ky3-sDAAA`
			}}

		/>
		
		<Action
			do={async () => {
				await code13.selectLines`7, 13`
                await code14.update`http://localhost:5174/return-data?d=1-H4sIAAAAA...1_ky3-sDAAA
                
host string:        http://localhost:5174
routing path:       /return-data
search parameter:   ?d=
GCscript data:      1-H4sIAAAAA...1_ky3-sDAAA
                `
			}}
		/>

	</Slide>


	<Slide class="h-full place-content-center place-items-center">
		<!-- Receiving data -->
		<p class="text-4xl font-bold drop-shadow-sm">Receiving data</p>
		<p>&zwnj;</p>
		<div class="flex flex-row gap-8">
		<div id="code-single" style="font-size: 62px;">
			<Code bind:this={code11} lang="javascript" theme="github-dark" code={``} />
		</div>
        <div id="code-single" style="font-size: 62px;">
			<Code bind:this={code12} lang="bash" theme="github-dark" code={``} />
		</div>
    </div>
		<Action
			do={async () => {
				await code11.update`src/pages/Data.jsx:
import { useSearchParams } from 'react-router-dom'
import { useEffect, useState } from 'react'

const Data = () => {
  const [searchParams, setSearchParams] = useSearchParams();
  const [resultObj, setResultObj] = useState({});

  const gc = window.gc;

  async function decodeActionUrl(returnData) {
    const mydata = await gc.encodings.msg.decoder(returnData);
    setResultObj(mydata);
  }

  useEffect(() => {
    let returnData = searchParams.get("d");
    decodeActionUrl(returnData);
  }, []);

  window.close()
  return (<h1>Results</h1>)
};
export default Data;
`
await code11.selectLines`6, 17`
await code12.update`http://localhost:5174/return-data?d=1-H4sIAAAAA...1_ky3-sDAAA
                
host string:        http://localhost:5174
routing path:       /return-data
search parameter:   ?d=
GCscript data:      1-H4sIAAAAA...1_ky3-sDAAA`
await code12.selectLines`5`
			}}

		/>

	</Slide>


	<Slide class="h-full place-content-center place-items-center">
		<!-- Receiving data -->
		<p class="text-4xl font-bold drop-shadow-sm">Unimatrix listener</p>
		<p>&zwnj;</p>
		<div id="code-single" style="font-size: 55px;">
			<Code bind:this={code15} lang="javascript" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code15.update`src/services/UnimatrixListener.jsx:
import { useEffect } from 'react';
...
export const UnimatrixListener = ({
    gun,
    unimatrixId,
    pubKey }) => {

    const params = {
        CSL: CardanoWasm(),
        db: gun,
        dltTag: "cardano",
        networkTag: "preprod",
        id: unimatrixId,
        subPath: ["signTxs"] }

    useEffect(() => {
        (async () => {
            CardanoSync.onTxHashes({ ... });
        })();
    }, [unimatrixId]);
    return null;
}
export default UnimatrixListener;
`
await code15.selectLines`5-7`

			}}
		/>

        <Action
        do={async () => {
           
await code15.selectLines`10-15`

        }}

    />
    <Action
    do={async () => {
       
await code15.selectLines`19`

    }}
/>

<Action
do={async () => {
    await code15.update`src/services/UnimatrixListener.jsx:
import { useEffect } from 'react';
...
export const UnimatrixListener = ({ gun, unimatrixId, pubKey }) => {
    const params = { ... }

    useEffect(() => {
        (async () => {
            CardanoSync.onTxHashes({
                ...params,
                cb: async ({ txHashes, 
                             validationError, 
                             userError, 
                             timeoutError, 
                             store, 
                             node, 
                             stop }) => {
                ... })
        })();
    }, [unimatrixId]);
    return null;

    }
export default UnimatrixListener;
`
await code15.selectLines`9-18`

}}
/>

<Action
do={async () => {
    await code15.update`src/services/UnimatrixListener.jsx:
import { useEffect } from 'react';
...
export const UnimatrixListener = ({ gun, unimatrixId, pubKey }) => {
    const params = { ... }

    useEffect(() => {
        (async () => {
            CardanoSync.onTxHashes({ ... }) => {

                txHashes.forEach(txHash => {
                    CardanoSync.getTxHex({ ...params, txHash })
                        .then(({ txHex }) => { 
                            console.log("txHex", { txHex }) });

                    let vkHash = pubKey;
                    CardanoSync.getVkWitnessHex({ ...params, txHash, vkHash })
                        .then(({ vkWitnessHex }) => { 
                            console.log("witness", vkWitnessHex) })
                });
            })
        })();
    }, [unimatrixId]);
    return null;
    }
export default UnimatrixListener;
`
await code15.selectLines`11-20`

}}
/>


	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- HOME -->
		<p class="text-4xl font-bold drop-shadow-sm">Add the listener component</p>
		<p>&zwnj;</p>

		<div id="code-single" style="font-size: 58px;">
			<Code bind:this={code16} lang="javascript" theme="github-dark" code={``} />
		</div>

		<Action
			do={async () => {
				await code16.update`src/pages/Home.jsx:
import { useEffect, useState } from 'react'
import Gun from 'gun';
import UnimatrixListener from '../services/UnimatrixListener';

let peers = ["https://ar01.gamechanger.finance:2083/unimatrix/gun"]

const Home = () => {

  const gun = new Gun({ peers });
  let unimatrixId = "multisig_1234"
  let pubKey = "ded983764fdb27ff993ce0257e64e20cba99348ad3721a59e8c62819"

  return (
    <>
    <h1>Home</h1>
    
    <UnimatrixListener {...{
        gun,
        unimatrixId,
        pubKey }} />
    </>
  )
};

`
await code16.selectLines`4, 18-22`
			}}
		/>

		<Action
			do={async () => {
			
await code16.selectLines`6, 10-12`
			}}
		/>



	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- 301.1  -->
		<p class="text-4xl font-bold drop-shadow-sm">301.5</p>
		<p>&zwnj;</p>

		<Transition>
			<p class="pb-5 text-base font-bold drop-shadow-sm">Building a full dApp</p>
		</Transition>
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 1100px;" src="/assets/dao_overview.png" alt="Welcome" />
	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<!-- Receiving data -->
		<p class="text-4xl font-bold drop-shadow-sm">Getting state</p>
		<p>&zwnj;</p>
		<div id="code-single" style="font-size: 55px;">
			<Code bind:this={code17} lang="javascript" theme="github-dark" code={``} />
		</div>

<Action
do={async () => {
    await code17.update`src/pages/Home.jsx:
const Home = () => {

  const [daoInfo, setDaoInfo] = useState({})
  
	useEffect(() => {
		let getDaoInfo = JSON.parse(localStorage.getItem("daoInfo_0"));
		
		if (getDaoInfo === null) {
		  getDaoInfo = { name: "", address: "" }
		}
		
		setDaoInfo({ ...daoInfo, ...getDaoInfo })
	}, []);
	
	return (<></>)
};

export default Home;
`
await code17.selectLines`7,13`

}}
/>

	</Slide>

	<Slide class="h-full place-content-center place-items-center">
		<img style="height: 700px;" src="/assets/change_name.png" alt="Welcome" />
	</Slide>

<Slide class="h-full place-content-center place-items-center">
	<!-- Receiving data -->
	<p class="text-4xl font-bold drop-shadow-sm">Saving state</p>
	<p>&zwnj;</p>
	<div id="code-single" style="font-size: 65px;">
		<Code bind:this={code18} lang="javascript" theme="github-dark" code={``} />
	</div>

<Action
do={async () => {
await code18.update`src/pages/Home.jsx:
const Home = () => {

	async function handleDaoNameChange(event) {
	
	  console.log("Change name");
	
	  let changedDaoInfo = { ...daoInfo }
	
	  changedDaoInfo.name = event.target.value
	  setDaoInfo(changedDaoInfo)
	
	  localStorage.setItem("daoInfo_0", JSON.stringify(changedDaoInfo))
	
	}

return (
		<input type="text" 
					 onChange={handleDaoNameChange} 
					 defaultValue={daoInfo.name} />
)};

export default Home;	
`
await code18.selectLines`4,19,10`

}}
/>

<Action
do={async () => {
await code18.selectLines`8,13,20`

}}
/>


</Slide>

<Slide class="h-full place-content-center place-items-center">
	<img style="height: 1100px;" src="/assets/get_pubkey.png" alt="Welcome" />
</Slide>


<Slide class="h-full place-content-center place-items-center">
	<!-- Receiving data -->
	<p class="text-4xl font-bold drop-shadow-sm">Updating home</p>
	<p>&zwnj;</p>

	<div class="flex flex-row gap-8">
	<div id="code" style="font-size: 55px;">
		<Code bind:this={code19} lang="javascript" theme="github-dark" code={``} />
	</div>
	<div id="code" style="font-size: 55px;">
		<Code bind:this={code20} lang="javascript" theme="github-dark" code={``} />
	</div>
    </div>
<Action
do={async () => {
await code19.update`src/pages/Data.jsx:
const Data = () => {
		...
    useEffect(() => {
		    ...
        localStorage.setItem("daoInfo_0", 
                             JSON.stringify(daoInfo))
    }, [resultObj])
};
export default Data;	
`
await code19.selectLines`6,7`
await code20.update`src/pages/Home.jsx:
const Home = () => {

  const [daoInfo, setDaoInfo] = useState({})
  
	useEffect(() => {
	
    window.addEventListener('storage', () => {     

      setDaoInfo(JSON.parse(
            localStorage.getItem('daoInfo_0')) || {})
    });
    
	}, []);
	
	return (<></>)
};

export default Home;
`
await code20.selectLines`8`


}}

/>
</Slide>


<Slide class="h-full place-content-center place-items-center">
	<!-- Receiving data -->
	<p class="text-4xl font-bold drop-shadow-sm">Event trick</p>
	<p>&zwnj;</p>
	<div id="code-single" style="font-size: 65px;">
		<Code bind:this={code21} lang="javascript" theme="github-dark" code={``} />
	</div>

<Action
do={async () => {
await code21.update`src/services/UnimatrixListener.jsx:
localStorage.setItem("transactions_0", JSON.stringify(daoTx))
window.dispatchEvent(new Event("storage"));
`
await code21.selectLines`3`

}}
/>
</Slide>


<Slide class="h-full place-content-center place-items-center">
	<!-- Receiving data -->
	<p class="text-4xl font-bold drop-shadow-sm">Selecting a new wallet</p>
	<p>&zwnj;</p>
	<div id="code-single" style="font-size: 55px;">
		<Code bind:this={code22} lang="javascript" theme="github-dark" code={``} />
	</div>

<Action
do={async () => {
await code22.update`src/pages/Home.jsx:
const gcscript =
{
  "type": "script",
  ...
  "run": {
    "walletSetup": {
       ...
    },
    
    "walletSelect": {
      "type": "setCurrentWorkspace",
      "workspaceId": daoInfo.name + "_DAO"
    },
    "getAddress": {
      "type": "getAddresses",
    } 
    
  },
  "returnURLPattern": host + "/return-data?d={result}"
}
`
await code22.selectLines`11,15`

}}
/>
</Slide>

<Slide class="h-full place-content-center place-items-center">
	<img style="height: 700px;" src="/assets/doa_done.png" alt="Welcome" />
</Slide>

<Slide class="h-full place-content-center place-items-center">
	<img style="height: 1100px;" src="/assets/create_proposal.png" alt="Welcome" />
</Slide>



</Presentation>
