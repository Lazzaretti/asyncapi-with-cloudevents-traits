# AsyncAPI and CloudEvents with Traits

This repository describes how CloudEvents can be defined in AsyncAPI v3.

First thing that needs to be decided when we want to use CloudEvents is:
* Which CloudEvents type should be used?
  * Binary Mode
    * [Use a trait to defin the CloudEvents headers](./light-switch-events-binary-mode.yaml)
  * Structured Mode (entire event, attributes and data, are encoded in the message body)
    * Wich format does the payload has?
      * [JSON](./light-switch-events-structured-json.yaml)
      * Other (no examples, yet)

## Traits vs allOf
- To merge we use `traits`, a AsyncAPI specific feautre exactly introduced for this use case. It is discussed for such use cases in
  - https://github.com/asyncapi/spec/issues/108
  - https://asyncapi.slack.com/archives/C0230UAM6R3/p1712148557132589
  - https://github.com/asyncapi/spec/issues/1057
