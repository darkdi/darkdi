Backend for a living: 1C-Bitrix and Bitrix24, PHP, MySQL, fourteen years of it. Moscow. The rest of my time goes to a game and to other people's codebases.

### DarkVell

**[darkvell.ru](https://darkvell.ru)**

An open-source browser MMORPG. Phaser on the client, an authoritative NestJS server on the other side, TypeScript across npm workspaces. Authoritative means the server owns the world state and the client only asks: no trusting the browser about where you are or what you hit. That constraint is most of the interesting work, and it is why realtime PvP is the part I care about getting right.

### Reading other people's code

I contribute bug fixes and API documentation corrections to other people's projects. The bugs range from infinite recursion and broken Windows paths to object comparisons that throw on valid input and layer-name handling that silently skips work. Sometimes the mismatch is between a comment and a signature; sometimes it is between what the code is meant to do and what it actually does.

I use language-specific checkers to find suspicious patterns, then inspect each finding in context: the surrounding code, callers, and history. A checker result is a lead, not proof. For behavior changes, I reproduce the failure and add regression tests where practical, checking that they fail before the fix and pass after it. False positives go into a separate record so the tools can improve. The aim is a small, useful patch that a maintainer can verify.

### What came out of it

[Merged pull requests across open-source projects](https://github.com/search?q=is%3Apr+author%3Adarkdi+is%3Amerged&type=pullrequests), among them:

| Project | Contribution |
|---|---|
| **Apple — [Core AI Torch](https://github.com/apple/coreai-torch/pull/72)** | fixed infinite recursion when comparing non-Torch graphs |
| **Apple — [Swift Crypto](https://github.com/apple/swift-crypto/pull/463), [SwiftProtobuf](https://github.com/apple/swift-protobuf/pull/2162), [SwiftNIO HTTP/2](https://github.com/apple/swift-nio-http2/pull/562), [App Store Server Library](https://github.com/apple/app-store-server-library-node/pull/428)** | corrected API documentation to match the actual parameters, including nonce handling in decryption APIs |
| **[PHP](https://github.com/php/php-src/pull/23583)** | restored Windows path detection when loading extensions in phpdbg |
| [home-assistant/core](https://github.com/home-assistant/core/pull/178207) | config entry removal was not shielded from a client disconnect. A race, with tests, not a comment fix |
| [laravel/telescope](https://github.com/laravel/telescope/pull/1753) | merged by Taylor Otwell |
| [nlohmann/json](https://github.com/nlohmann/json/pull/5363) | merged by Niels Lohmann |
| **NVIDIA — [cuDF](https://github.com/NVIDIA/cudf/pull/23564)** | corrected Doxygen parameter and template-parameter documentation in the C++ API |
| [mrdoob/three.js](https://github.com/mrdoob/three.js/pull/34226) | stale JSDoc in the WebGPU renderer |
| [twisted/twisted](https://github.com/twisted/twisted/pull/12775) | eight epytext fields in the core |
| [saltstack/salt](https://github.com/saltstack/salt/pull/69966) · [tesseract](https://github.com/tesseract-ocr/tesseract/pull/4594) · [mlflow](https://github.com/mlflow/mlflow/pull/24925) · [astropy](https://github.com/astropy/astropy/pull/20205) · [FreeCAD](https://github.com/FreeCAD/FreeCAD/pull/31773) · [qutebrowser](https://github.com/qutebrowser/qutebrowser/pull/8995) · [Prefect](https://github.com/PrefectHQ/prefect/pull/22733) | the rest of the same work |

Open pull requests: [**Google SAM**](https://github.com/google/sam/pull/340) — clarify the required service type in the discovery tool schema; [**Apple Embedding Atlas**](https://github.com/apple/embedding-atlas/pull/253) — prevent deep equality checks from crashing on null-prototype objects or a shadowed `hasOwnProperty`; [**NVIDIA Model Optimizer**](https://github.com/NVIDIA/Model-Optimizer/pull/2345) — fix layer-name truncation that silently skips selected layers during sparsity processing. The latter two include regression tests.

Three rules I did not have at the start and would not drop now. Read the project's own policy on AI assistance before touching the code, and follow it even when nobody would check. One pull request per project per day, because twelve in a day reads as a campaign no matter how correct each one is. And write the description by hand: if a sentence can be verified by opening the diff, it does not belong in the description.

[rant.ae](https://rant.ae) · Telegram [@rant_root](https://t.me/rant_root)
