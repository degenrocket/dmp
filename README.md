# Deprecated

DMP is superseded by [Spasm](https://github.com/degenrocket/spasm).

# Degen Messaging Protocol (DMP)

A public communication protocol for a degentralized censorship-resistant network with optional moderation enabled on a client or node side.

## General schema

### Version 0.1.0

```
{
    "version": <string>,
    "time": <string>,
    "action": <string>,
    "target": <string>,
    "text": <string>,
    "license": <string>,
}
```
### Actions

An action can be:

* `post` to create a new post,

* `reply` to create a comment,

* `react` to create a reaction, e.g. `upvote`, `downvote`, 

* `edit` to create a new version of an action/event, which can be optionally shown on a client alonside of instead of an original action/event,

* `moderate` to moderate an action/event, e.g. `hide`,

* `share` to boost/repost an action/event.

Examples of valid actions:

```
"action":"post"
"action":"reply"
"action":"react"
"action":"edit"
"action":"moderate"
"action":"share"
```

### Targets

A target can be:

* an ID of an action/event (equals to its signature in DMP),

* any public key,

* a media file hash (torrent, IPFS),

* a URL,

* any other string.

Examples of valid targets:

```
// an id of an action/event (equals to its signature in DMP)
"target":"0xbd934a01dc3bd9bb183bda807d35e61accf7396c527b8a3d029c20c00b294cf029997be953772da32483b077eea856e6bafcae7a2aff95ae572af25dd3e204a71b"

// any public key
"target":"0xf8553015220a857eda377a1e903c9e5afb3ac2fa"

// a sentence
"target":"code is free speech"

// a word
"target":"ivermectin"

// a protocol version
"target":"dmp_v0.1.0"
```

### Licenses

To avoid any potential legal responsibilities for distributing the copyright-protected content, the Creative Commons Zero v1.0 Universal (CC0-1.0) license should be added to each signed action/event by default. (Here is a license-related [discussion](https://github.com/nostr-protocol/nips/pull/857) regards to the Nostr protocol.)

Users might choose different licenses, and then the network participants can decide whether to accept or reject such actions/events.

Example:

```
"license":"SPDX-License-Identifier: CC0-1.0"
```
