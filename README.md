# AsyncAPI with CloudEvents Traits

This repository describes how CloudEvents can be defined in AsyncAPI v3. It was created as a follow-up after discussion [cloudevents/spec#1276](https://github.com/cloudevents/spec/issues/1276).

The first thing that needs to be decided when we want to use CloudEvents is:
* Which CloudEvents type should be used?
  * Binary Mode
    * Use a trait to define the CloudEvents headers; they are different for each binding
      * [Kafka bindings](./traits/cloudevents-headers-kafka-binary.yaml)
        * [Kafka example with binary mode](./light-switch-events-binary-mode.yaml)
      * Other (no examples, yet)
  * Structured Mode (entire event, attributes, and data are encoded in the message body)
    * Which format does the payload have?
      * [JSON](./light-switch-events-structured-json.yaml)
      * Other (no examples, yet)

## Traits vs allOf
- To merge different headers, we use `traits`, an AsyncAPI-specific feature introduced exactly for this use case. It is discussed for such use cases in:
  - https://github.com/asyncapi/spec/issues/108
  - https://asyncapi.slack.com/archives/C0230UAM6R3/p1712148557132589
  - https://github.com/asyncapi/spec/issues/1057
