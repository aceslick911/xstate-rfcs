- **Start Date:** 2022-06-24
- **RFC PR:**

# Use WebRTC as a communication layer option for @xstate/inspect and a unified cross-platform medium for actor messaging & service-discovery

## Summary

Utilizing WebRTC (https://webrtc.org/) as an communication layer option for both (1)Inspecting Actors and (2)Actor-actor communication can be secure, both discoverable & decentralised and enable a standard, consistent and reliable capability to access, orchestrate and debug actors running in varying languages, operating environments & network condition.

## Motivation

The motivation of this RPC is to engage the core team and community about the benefits and opportunities of:

1. Enabling webRTC communications for a secure & standardised method of discovering, inspecting, debugging & monitoring of XState actors in environments such as browsers, mobile apps, local and remote nodeJS instances and

2. Creating a core-supported WebRTC protocol for `Actor discovery` (service discovery) and `Actor-Actor Messaging` (messaging) with cross-platform client examples in other programming laguages & frameworks (eg. python/.net/rust) for other operating environments such as docker containers/kubernetes, IoT devices, embedded & edge computing systems.

I believe by utilizing the `enhanced network connectivity` capabilities of WebRTC (abillity to get around common NATs and firewalls whilst enabling secure messaging and streaming data transfer), and ability to `facilitate service discovery` (ICE Channels) - it will enable an expansion for both the ability to `inspect actors` as well as the ability to take on responsibilities as an effective `orchestration hub`.

## Detailed design

### Technical Background

`@xstate/inspect` currently supports `window.postMessage()` or Websockets `options: { server: new WS("localhost:1234")}` as the communication layer between a running machine actors with devtools enabled.

This works sufficiently for web front-end applications (postMesasage interprocess communications is fast and efficient) but can be difficult and not consistently secure or possible (websockets must open a port on localhost) to implement for nodeJS services (using websockets in ).

webRTC is a widely used protocol for peer-to-peer communications on the web and has good support across Desktop browsers.

## Browsers

Source: https://caniuse.com/?search=webrtc

- Edge 79+
- Firefox 22+
- Chrome 23+
- Opera 18+
- Safari (Desktop & iOS) 11+
- Android Browser (Android 5+, Chromium 101)

## Native on Devices & Operating Systems

- Xcode 10+
- macOS 10.15+
- iOS 12+

## Programming Language / Framework native support

- Python
- .Net
- Java
- C++

Formalizing a supported and consistent protocol for utilizing WebRTC for communications between `@xstate/inspect` and Viz (xstate, stately, or custom) can ensure developers adapt implementations that are consistently secure, avoid re-inventing proven patterns and can deploy supported, constantly improved & patched production systems.

# Discoverability

- Discover & Monitor actors associated with a unique WebRTC ICE Channel Label

# Networking Features

- Secure communications

  - SSL

- Estabilishing p2p communication using ICE

  - Enables communication even when behind one or more NATs

- TURN Servers to bypass blocking p2p firewalls

# Distributed Systems

# Language-agnostic RPCs & Cross-platform Orchestration

As XState was originally developed in Javascript (browser), it is a well-supported tool capable of writing, maintaining and managing machines but primarily for the browser only.

Whilst there is continual interest and improving implementations for statecharts & x-state's implementation of statecharts in other languages (python, .net, rust, etc.); it is a duplication of core efforts that may not scale with the intention to create interoperable systems that are consistent in operation. This can lead to fragmentation of supported features and forks in execution details that will make implementation knowledge in one language/framework difficult to translate to another.

### Implementation

This section is split into two specific uses of the WebRTC specification in XState

- Inspecting XState Actors with WebRTC
  - Access instances without needing websockets servers
- Orchestrating XState Actors with WebRTC
  - Actor-Actor Messaging
  - Service discovery

## How we teach this

### WebRTC specification basics

### Routing

## How do we type this

### Channel Abstractions

###

## Drawbacks

### Bottlenecks

### Requirement for 3-Step signalling

### Bandwidth requirements or limits when needing TURN servers

### Security concerns

## Alternatives

> What other designs have been considered? What is the impact of not doing this?

> This section could also include prior art, that is, how other frameworks in the
> same domain have solved this problem differently.

## Unresolved questions

> Optional, but suggested for first drafts. What parts of the design are still to be decided?
