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
