---
title: 'Fortune'
coverImage: '/assets/projects/fortune-screenshot.png'
excerpt: 'A (eventual open-source) metaverse engine that lives on the web for interconnected experiences, integrated with web3 authentication and NFTs for persistent storage of player profiles and inventories.'
date: '2022'
createdDate: '2022'
tags: 'typescript,metaverse,llms,web3,nfts'
# author:
#   name: Johnny Dunn
#   picture: '/assets/blog/authors/jj.jpeg'
ogImage:
  url: '/assets/projects/fortune-screenshot.png'
---

<a href="https://fortune.day" style="text-align: center" target="_blank" class="md-link">Link</a>

<a href="#" style="text-align: center; color: grey" target="_blank" class="md-link">GitHub (Coming Soon)</a>

<a href="https://fortune.day/whitepaper/" style="text-align: center" target="_blank" class="md-link">Whitepaper</a>

<a href="https://fortunemeta.gitbook.io/fortune-metaverse-engine/" style="text-align: center" target="_blank" class="md-link">Docs</a>

## Intro

Fortune is a metaverse engine system that links interconnected experiences on the web (as `worlds` or `rooms`, which can have `subrooms` in a recursive data structure), with shared player profiles and inventory states.

This version was designed to be decentralized, and will utilize smart contracts (NFTs) for storing items across worlds in the metaverse. Authentication is done through web3 wallets. Eventually, a version that is centralized and uses conventional cloud databases and user authentication might be developed, to reach an audience beyond web3-oriented users.

Fortune was built off of and is the next evolution of my project <a class="md-link" href="https://jddunn.github.io/projects/text-rpg-engine/" target="_blank" style="margin-left: 0; margin-right: 0; display: inline">text-rpg-engine</a>. It will eventually be open-sourced when the platform code and documentation is finished (currently in-progress).

*Any* type of interactive experience can be created in Fortune, as it is all powered by web code (HTML, CSS, JS). Script and stylesheet files are injected dynamically into the UI on each room load, then removed when the player exits that room, though player profiles and inventories can persist throughout every room / world. Multiplayer and online functionality is supported through websockets, and the data of the metaverse lives in JSON files.

## Technical details

The metaverse engine is written in JavaScript / TypeScript, as a ES6 library. It can be transpiled into a bundled JS file with the data contents of the metaverse that gets ingested, so it can be run and hosted by a static server, without the need to load the metaverse data files. 

The metaverse data / game worlds can be created programmatically with an API, or dynamically loaded from JSON files (see <a class="md-link" href="https://fortune.day/example.json" target="_blank" style="margin-left: 0; margin-right: 0; display: inline">this link</a> to see the data that makes up Fortune's demo metaverse on its site).

A server that runs services for websocket communications supports chatting functionality and other online cooperative functionalities that can be utilized by scripts that creators write for their game worlds and rooms.

NPCs can be created for Fortune worlds (for purposes like role-playing and immersive storytelling) which are powered by LLMs like OpenAI's GPT models, though there are no demos created showcasing this yet publicly and this is still a WIP.

The metaverse UI on Fortune's site will also be open-sourced, and it is currently written using HTML, CSS, Bootstrap, and JavaScript / TypeScript. It will be rewritten to utilize React / Next for its open-source release.

## Features

### Interconnected worlds and recursive rooms

Worlds and rooms in Fortune's metaverse can be connected and linked, allowing players to navigate from world to world with the appropriate prompt action. Players can also navigate inner rooms or subrooms within a world or room with prompts as well. Subrooms have a recursive structure so they can contain other subrooms indefinitely.

The data of the worlds are contained in a single or multiple JSON files (JSON files can be segmented and linked together so the metaverse can scale with optimized mechanisms of searching for and loading files, or ingested and handled through a hosted database, with connections between worlds defined within the data as links between unique names / IDs).

### Text adventures / interactive fiction mechanics

Any type of interaction can be abstracted through the textual mechanics of Fortune's metaverse worlds. Creators can define different prompts with actions that can load new contents to render, give and remove items in the player's inventory, and transfer them to new rooms and worlds. These prompts can be hidden away from the user or shown as buttons or carousel card components. Prompts can also have item requirements, and be hidden and revealed once a player reaches those requirements.

This makes Fortune very well-suited for text adventure games and interactive fiction.

<a href="/assets/projects/fortune-text-adventure-demo.gif" target="_blank"><img src="/assets/projects/fortune-text-adventure-demo.gif" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune text adventure demo"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Prompts can have their display turned off in the UI, to emulate a classical text adventure experience. Prompts can be shown in a moving carousel to provide an aesthetic way of navigating through rooms.</span>

### Web3 authentication

Users can login with a Metamask wallet in order to take advantage of features like cooperative and online support, as well as for persistent storage of items and stats within smart contracts (which will also be open-sourced).

<a href="/assets/projects/fortune-web3-wallet.png" target="_blank"><img src="/assets/projects/fortune-web3-wallet.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune web3 wallet connection"></img></a>

### Chatrooms

Each world and room in Fortune is given its own chatroom that exists separately from other chatroom instances from other worlds. Players can only visit a chatroom once they have reached and navigated to that specific room, and they can navigate back to other chatrooms tied to rooms they've already explored.

Players must authenticate with their web3 wallet to be connected to the chatrooms, and their usernames are their wallet addresses.

Chatting functionality includes speech synthesis and recognition support using the SpeechRecognition and SpeechSynthesis APIs. You can also tag users in the chatroom messages, and receive notifications on mentions.

<a href="/assets/projects/fortune-chatrooms.png" target="_blank"><img src="/assets/projects/fortune-chatrooms.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune chatrooms"></img></a>

### Web experiences (apps and games)

Fortune worlds and rooms will render the HTML contents a creator defines either directly in the JSON data, or from a local HTML file (on the server hosting Fortune's metaverse) or an online HTML file link. Stylesheets and scripts can also be loaded locally on the server or from online links, and those files will be appended to the page's head when a user enters the room containing those dependencies. When the user exits, those file dependencies are removed from the page's head. This allows Fortune to support the creation of and render any type of web-based experience, app, or game.

<a href="/assets/projects/fortune-crypto-charts-and-news.png" target="_blank"><img src="/assets/projects/fortune-crypto-charts-and-news.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune crypto charts and news room"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Web app for comparing crypto charts and news that uses a crypto pricing API in Fortune</span>

<a href="/assets/projects/fortune-wikipedia-reader.png" target="_blank"><img src="/assets/projects/fortune-wikipedia-reader.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune Wikipedia reader"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Web app for reading Wikipedia articles in Fortune</span>

<a href="/assets/projects/fortune-ascii-rogue-demo.gif" target="_blank"><img src="/assets/projects/fortune-ascii-rogue-demo.gif" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune Roguelike demo"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Web game of a Roguelike horror game with ASCII aesthetics in Fortune</span>

<a href="/assets/projects/fortune-poker-demo.gif" target="_blank"><img src="/assets/projects/fortune-poker-demo.gif" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune Poker demo"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Web game of Poker in Fortune with AI bots and multiplayer functionality</span>

### Online and cooperative multiplayer support

Online functionality and cooperative player interactions are supported through a hosted server that runs websockets open for worlds / rooms within the metaverse to communicate. Creators will call the websocket server's messaging system (which will be detailed in the room creation docs) in their scripts they create for their rooms to implement multiplayer features.

Creators must be whitelisted with their wallet addresses on the websockets server to utilize it. 

<a href="/assets/projects/fortune-watchparty-1.png" target="_blank"><img src="/assets/projects/fortune-watchparty-1.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune Watchparty demo 1"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Example online multiplayer Fortune world called Watchparty, that allows players to watch videos together synchronously</span>

<a href="/assets/projects/fortune-watchparty-2.png" target="_blank"><img src="/assets/projects/fortune-watchparty-2.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="800" alt="Fortune Watchparty demo 2"></img></a>
<span style="text-align: center; color: grey; margin-left: auto; margin-right: auto; display: block; width: 80%">Watchparty room joined with two players watching something simultaneously; each player can move and pause the video on their end and it will change the playback for everyone.</span>

### AI NPCs

Eventually, Fortune worlds can incorporate dynamic gameplay mechanics with AI NPCs using generative AI techniques using LLMs. This will greatly empower creators in the creation of their worlds, and allow for immersive and complex narrative building.

## Future

The roadmap is still unknown for Fortune's future. Development will continue (by myself and the help of other developers I can find, though no team has been assembled yet) until all the planned functionality has been created, and the creation system for game worlds for the metaverse is robust enough to go public for finding content creators and game developers. 
