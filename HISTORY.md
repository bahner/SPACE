# SPACE - Spaces for Punk Actors in Cybernetic Entities

## lambdaMOO

This project stems from having spent time with [NOOD] in [lambdaMOO] back in the good old days.

I have been thinking about using the MOO style of programming to do actual work. Imagine working as a webmaster and there is something wrong with a vhost. You page Alica and request that shes meet you in the "server room". Alice arrives and asks what the problem is and you say that Bob's website is offline.

She looks at the changelog for Bob's vhost and notices that Someone™ made changes to it yesterday. The port was changed from 443 to 4443 along with some other changes. She fixes the port number, and ask me if I agree. I sign of one the changed vhost and the change is commited and recompiled. Bob's website is back online.

The thing here is that by using space metaphors you can be *inside the computer program*. I'm talking The Matric and Tron here. The one that made the changes could very well have been a robot avatar that someone hooked up to ChatGPT. Also the fact, that we meet and discuss the actual working "object" or "thing" means that there is no pipeline or code that has to be changed. No searhing for the correct code repository. If we need permission to change the code, we can just invite the person with the correct permissions to the room. And we can discuss the actual thing that is broken. Not some abstract code in an office far, far away.

What NOOD and others did was to implement software on top of lambdaMOO. The mighty [DRGN]. This software was used to syncronise MIDI sequences across the globe. I believe [RRS] had thousand members at it's peak. If something was "off" they could go to the DRGN room and look at the code an fix it. In realtime. This was in the early 90's. And it was a revelation.

Back then I thought [Scheme] was cooler than strawberry jam and I played with the idea of implementing a MOO in scheme, using scheme itself as the programming language, but I never got around too it.

Someone else actually wrote some [Scheme MOO's][schememuds] since then.

### Mooix / room.js

Then Joey Hess wrote [Mooix] and it was like someone turned on the light. I find his architecture to be absolutely brilliant, even though it's kind off simple in it's basic architecture. I was eagerly waiting for him to publish his Mooxix NG, but it never materialsed. When one looks back at it know, that was probably a good idea, but with the advent of libp2p I think his general idea can probably be made a reality. I believe his ideas resemble what I'm trying to achieve here.

I also found [room.js][roomjs] to be a very interesting project. I was blown away with the fact that it looks like it's run in the browser and that you can program it directly. Being written in JavaScript kinda takes the fun out of it for me.

I like the [room.js client][roomjsclient], though and maybe I'll fork an rewrite it has the initial client for this project.

## Alphaworld

Working at [WIT] I researched the possibility of creating a virtual world for the company. I looked at [Alphaworld] written by [Ron Britvich][ron] and was blown await with very manageable, relatively user friendly tech. Also he used url's everywhere. All external resources was added with URLs. There were a few others technolgoies and VRML implementions, but none of them matched the actual online, functioning world that Alphaworld was.

We started building [Patagonia][pata] as a virtual world using Blade Runner's dark dystopia as inspiration and it was great. It was later sold and replaced by another world Patagonia[patb]. To be fair all the actual work was done by [Henrik Gudbrandsen][henrikg] and other volunteers and he continued to work on it for years after it was sold. I think it's still up and running.

While this was fun and VR was an actually useful tool, business crept in and suddenly it wasn't fun anymore. But more importantly it was all cosmetic. You couldn't actually program the world that much and you couldn't use it for anything useful. It was just a 3D world.

Obviously the experiment was repeated later with Second Life. Again it shows that such worlds can't exist and evolve when under the control of a single entity. It's just not possible. It's not fun. It's not useful. I predict Meta's Metaverse will fail for the same reason.

What might work in this space is [Mozilla's Hubs][hubs]. Not that's cool. But it's still not a real metaverse. It's just a 3D world.

## Web 2.0

In a nutshell such a web of worlds wasn't possible with Web 2.0 tech. But now with libp2p and IPFS it might be possible. I think it's worth a shot.

## Metaphors

The thing is it was never really about writing or using a MUD, but to have a home in cyberspace. I find it a little sad that homepages don't exist anymore. I think it's important to have a place to call your own. A place where you can be yourself. A place where you can be creative.

## DID's

By using DID's and IPNS names and storing data in IPFS and using IPLD, we should be able to store such MOO's in IPFS and have them communicate over the Sub-Etha™ waveband. This means that by using pinning in IPFS, it should be possible to open a world with two variables: an encoded secret key and the root CID of a world.
This also means that you can run a world in any browser on a system with IPFS installed. Or just use [Brave Browser][brave], you know.

This means that you don't strictly need servers to run a world. You can run it in your browser. Or you can run it on a server. Or you can run it on a Raspberry Pi. What is important is that you can run it anywhere. On your phone, on your laptop, or whatever.

This is truely distributed, if it works.


### The Sub-Etha™ Waveband"

### The Matrix / Tron


So [Hewitt's Actor model][hewitt] and Erlang comes into play here. The Sub-Etha™ waveband is used to send messages bewteen objects. And objects will initially be implemented in Elixir. But the Sub-Etha™ waveband is language agnostic.

The way this works is that each object has a - unique - IPNS name and also listens on the libp2p gossipsub network for messages to a topic of the same name as the IPNS name.

So if you want to send a message to an object, you send it over gossipsub to a topic with the name of the IPNS name of the object. The object will then receive the message and act on it.

The message is a DIDComm resembling message. Heck. Maybe it is those specs are so insanely complicated that I don't want to read them. But the gist of it is that it's a JSON message with a type and a payload. The payload is an encrypted message encrypted to the public key of the object, so only
the object should be able to open it.

## Idea

What I personally want to use this for is to build a mesh of MOO's, as in [LambdaMOO][lambdamoo]. I find the lambdaMOO to be some of the moso interesting technology ever. It's brilliant.

It's a shame that it's not used more. If we could interconnect these world, we would have an actual metaverse, not the silly 3D worlds touted as such.

For the metaverse to be a real thing, you should be able to from Wow to Second Life with out any problems. And you should be able to use your avatar in any world. And you should be able to use your objects in any world. And you should be able to use your code in any world.

You should be able to move freely between them.

## Technicalities

### Elixir

I intended to create the entire POC in Elixir, but libp2p in Elixir is pretty dead at the moment. So I decided to do it in Go. I have never written a single line of Go before, so this is a learning experience for me. I have written [IPFS], [IPNS] and [IPLD] libraries for Elixir. But a libp2p implementation is not feasible in the foreseeable future. At least for one person. So I decided to do it in Go. These structs and functions are the result of that decision. They will be consumed by another project - [go-space] - which is an erlang node that will be used to communicate with the Go Sub-Etha™ tools and integrate with the Elixir world.
So go-space will do all the libp2p gossiping, and Elixir will host all the actually objects. This is a good separation of concerns, I think.
## IPFS

By leveraging IPFS you can sit an write your code anywhere and publish it to IPFS. Then you can just update your objects content attribute to point to that CID. This means that code reuse and the programming environment is completely distributed. You can just use any code you want, and you can just publish your code to IPFS and use it. No need for a server. No need for a central authority. Just publish your code and use it.

This obviously raises some security concerns. Which is why we need encryption and authentication. This is achieveable by adding more DIDs. This can be solved by using DID's in a smart way to carry ACLs. But that's not an issue for the Sub-Etha™ part of the equation.

### Go

2023-09-18: bahner

[brave]: <https://brave.com/> "Brave Browser"
[go-space]: <https://github-com/bahner/go-space> "Go SPACE™"
[IPFS]: <https://hex.pm/packages/ex_ipfs> "Elixir IPFS"
[IPNS]: <https://hex.pm/packages/ex_ipns> "Elixir IPNS"
[IPLD]: <https://hex.pm/packages/ex_ipld> "Elixir IPLD"
[mooix]: <https://joeyh.name/code/mooix/> "Mooix"
[roomjs]: <https://github.com/doughsay/room.js/> "room.js"
[hewitt]: <https://arxiv.org/vc/arxiv/papers/1008/1008.1459v8.pdf> "The Actor Model (everything you wanted to know)"
[erlang]: <https://www.youtube.com/watch?v=xrIjfIjssLE> "Erlang: The Movie"
[did]: <https://www.w3.org/TR/did-core/> "Decentralized Identifiers (DIDs) v1.0"
[didcomm]: <https://identity.foundation/didcomm-messaging/spec/> "DIDComm Messaging v1.0"
[smalltalk]: <http://stephane.ducasse.free.fr/FreeBooks/BlueBook/Bluebook.pdf> "Smalltalk-80: The Language and its Implementation"
[Io]: <https://iolanguage.org/> "Io"
[pharo]: <https://pharo.org/> "Pharo"
[squeak]: <https://squeak.org/> "Squeak"
[oopsla]: <https://www.youtube.com/watch?v=ubaX1Smg6pY> "The computer revolution hasn't happened yet"
[alt.pave.the.earth]: <https://alt.pavethe.earth/> "Frequently Asked Questions for alt.pave.the.earth"
[elixir]: <https://elixir-lang.org/> "Elixir"
[nood]: <https://www.discogs.com/release/225621-Nood-Hettylettynetty> "Nood - Hettylettynetty"
[rrs]: <http://www.jamwith.us/about_us/rocket_history.shtml> "Res Rocket Surfer"
[DRGN]: <https://quod.lib.umich.edu/i/icmc/bbp2372.1995.126/2/--distributed-real-time-groove-network-a-system-for-real-time?page=root;size=125;view=text> "Distributed Real-Time Groove Network: A System for Real-Time Computer Music"
[moocode]: <https://www.hayseed.net/MOO/manuals/ProgrammersManual.html> "MOO Programmer's Manual"
[sicp]: <https://www.youtube.com/watch?v=-J_xL4IGhJA&list=PLE18841CABEA24090&t=14s> "Structure and Interpretation of Computer Programs"
[Actors]: <https://www.youtube.com/watch?v=7erJ1DV_Tlo> "Actors: The Universal Primitive"
[BEAM]: <http://www.cs-lab.org/historical_beam_instruction_set.html> "BEAM Instruction Set"
[NOOD]: <https://www.liveart.org/nood/newindex.html> "Nood"
[lambdaMOO]: <https://www.cc.gatech.edu/classes/cs8113e_99_winter/lambda.html> "lambdaMOO"
[Scheme]: <https://groups.csail.mit.edu/mac/projects/scheme/> "Scheme"
[schememuds]: <http://tunes.org/wiki/scheme.html> "Scheme MUDs"
[TUNES]: <http://tunes.org/> "TUNES"
[phantomos]: <http://phantomos.org/> "Phantom OS"
[Guix]: <https://guix.gnu.org/> "Guix"
[WIT]: <https://wit.no/> "Web InfoTech AS"
[pata]: <https://wiki.activeworlds.com/index.php?title=Pata> "Patagonia"
[Alphaworld]: <https://wiki.activeworlds.com/index.php?title=Alphaworld> "Alphaworld"
[ron]: <https://britvich.com/> "Active Worlds"
[henrikg]: <https://www.facebook.com/henrik.gudbrandsen> "Henrik Gudbrandsen"
[hubs]: <https://hubs.mozilla.com/> "Mozilla Hubs"
[roomjsclient]: <https://github.com/doughsay/room.js-client> "room.js client"